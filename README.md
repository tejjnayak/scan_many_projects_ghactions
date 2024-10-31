Step 1:

Fork the repo into your org: https://github.com/Endor-Solutions-Architecture/scan_many_projects_ghactions

Step 2:

You need to create 3 secrets on this repo: 

GH_TOKEN
ENDOR_API_CREDENTIALS_KEY
ENDOR_API_CREDENTIALS_SECRET 

GH_TOKEN:
Go into your github profile settings->developer settings->Fine-grained tokens->generate token. 

Make sure you give read access to code, metadata as permissions. 

Create Endor Labs API keys with code scanning permissions at: https://app.endorlabs.com/t/your_namespace/access/api-keys
Add those 3 values into your project settings as secrets:

Step 3:

Edit .github/workflows/scan.yml so that it has the names of the secret that you choose on the settings. Also change the value of ENDOR_NAMESPACE to be your_namespace

Also change line 23 to match your secret name: 
token: ${{ secrets.YOUR_GITHUB_PERSONAL_TOKEN }}

Step 4:
Edit the repo_list.txt and include your repos one per line, url should end in .git

As soon as you save the file it will automatically start the process or you can trigger the process manually. Once we do the POC we can enable it as a cron job to run every night. 

NOTE: Because this is a forked repo, you will have to enable the actions, this is msg will show when you click the actions tab. 
