Quickly scan repos outside your org or inside your org. You load in a list of repo urls and let it running, instead of having to do it one by one manually. 
Use case: If you need to add in a build step for each repo you can do so on the line that says #ADD ANY CUSTOM BUILD STEPS YOU NEED HERE

Step 1:

Fork the repo into your org: https://github.com/Endor-Solutions-Architecture/scan_many_projects_ghactions

Step 2:

You need to create secret on this repo: GH_TOKEN

GH_TOKEN:
Go into your github profile settings->developer settings->Fine-grained tokens->generate token. 

Make sure you give read access to code, metadata as permissions. 

Step 3:

Edit .github/workflows/scan.yml so that it has the names of the secret that you choose on the settings. Also change the value of ENDOR_NAMESPACE to be your_namespace

Also change line to match your secret name: 
token: ${{ secrets.YOUR_GITHUB_PERSONAL_TOKEN }}

Step 4:
Edit the repo_list.txt and include your repos one per line, url should end in .git

As soon as you save the file it will automatically start the process or you can trigger the process manually.

NOTE: Because this is a forked repo, you will have to enable the actions, this is msg will show when you click the actions tab. 
