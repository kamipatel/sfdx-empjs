# Prerequisites
1. Download and install Visual Studio Code from https://code.visualstudio.com/  
2. Download and install SFX CLI from https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_install_cli.htm  
3. In, Visual Studio install the 'Salesforce Extension Pack' extension  
4. Add "Replication" and "AntiPhishingSystem" configs to your dev.xml  (Optional)
5. Update instanceUrl in sfdx-project.json to point to your local app server  
  
  
# Steps
1. **Create a new Developer Hub**  
`sfdx alt:org:create --type developerhub --companyname MyLocalDevHub --email vkommaraju@salesforce.com --username vk@dev.com --mydomain MyDomain --password test1234`  
  
2. **Create OAuth Consumer for org to enable Salesforce Developer Experience**  
`sfdx alt:sfdx:enable --orgid 00Dxx00000070yd`  
  
3. **Authorize the new org with the consumer**  
  
*On Localhost Enter **1384510088588713504** when prompted for Oauth client secret*  
`sfdx force:auth:web:login --setalias MyScratchOrg --instanceurl http://vkommaraju-wsl1.internal.salesforce.com:6109 --setdefaultusername -i SalesforceDevelopmentExperience`  
  
*Production/Sandox*  
`sfdx force:auth:web:login --setalias MyScratchOrg --setdefaultusername`  

# Deploying new changes
**Deploy changes from src/main directory using**    
`sfdx force:source:deploy --json --loglevel fatal --sourcepath default`

# References   
**SFDX Local Setup Instructions Doc**  
https://docs.google.com/document/d/1vSVdxnTJjqyUCEBR8gz-ncfPgKmnvV6MbS8ZFI83GiE/edit#heading=h.4d4vzeyu3ey1  
**LWC Trailhead**  
https://trailhead.salesforce.com/content/learn/projects/quick-start-lightning-web-components?trail_id=build-lightning-web-components  
**LWC Recipes**  
https://github.com/trailheadapps/lwc-recipes/
