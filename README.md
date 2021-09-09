# TheCodeAttic.ACRTask.SitecoreImages

Files to Support ACR Task to automate Sitecore Image builds.

## Task Create Scripts

To help facilitate smaller task runs as well as allow for commit triggers to for specific images, multiple branches have been created tied to a similarly named task file.

The mapping is

**Task YAML** | **Branch** | **Notes**
--------------|-------------|-----------
sc-base-image | main | will run builds for all images
sc-base-cd | cd | use to create CD images
sc-base-cm | cm | use to create CM images
sc-base-solr | solr | use to create solr-init images
sc-base-sql | sql | use to create SQL images
sc-base-services | services | use to create XDB related services, such as XConnect

Following are the basic task create commands you will need to run.

Be sure to fork this repository before connecting it to an ACR Task, or my commits will trigger builds in your environment, which I do not think you'll want.

```powershell

# Create code commit trigger task
az acr task create `
  -n SitecoreBaseImages-All `
  --registry thecodeatticimages `
  --file sc-base-image.yml `
  --context 'https://github.com/gillissm/TheCodeAttic.ACRTask.SitecoreImages.git#main' `
  --platform windows/amd64 `
  --commit-trigger-enabled false `
  --base-image-trigger-enabled false `
  --git-access-token <Personal_Access_Token>

az acr task create `
  -n SitecoreBaseImages-CD `
  --registry thecodeatticimages `
  --file sc-base-cd.yml `
  --context 'https://github.com/gillissm/TheCodeAttic.ACRTask.SitecoreImages.git#cd' `
  --platform windows/amd64 `
  --commit-trigger-enabled true `
  --base-image-trigger-enabled true `
  --git-access-token <Personal_Access_Token>

az acr task create `
  -n SitecoreBaseImages-CM `
  --registry thecodeatticimages `
  --file sc-base-cm.yml `
  --context 'https://github.com/gillissm/TheCodeAttic.ACRTask.SitecoreImages.git#cm' `
  --platform windows/amd64 `
  --commit-trigger-enabled true `
  --base-image-trigger-enabled true `
  --git-access-token <Personal_Access_Token>

az acr task create `
  -n SitecoreBaseImages-Services `
  --registry thecodeatticimages `
  --file sc-base-services.yml `
  --context 'https://github.com/gillissm/TheCodeAttic.ACRTask.SitecoreImages.git#services' `
  --platform windows/amd64 `
  --commit-trigger-enabled true `
  --base-image-trigger-enabled true `
  --git-access-token <Personal_Access_Token>

az acr task create `
  -n SitecoreBaseImages-Solr `
  --registry thecodeatticimages `
  --file sc-base-solr.yml `
  --context 'https://github.com/gillissm/TheCodeAttic.ACRTask.SitecoreImages.git#solr' `
  --platform windows/amd64 `
  --commit-trigger-enabled true `
  --base-image-trigger-enabled true `
  --git-access-token <Personal_Access_Token>

az acr task create `
  -n SitecoreBaseImages-SQL `
  --registry thecodeatticimages `
  --file sc-base-sql.yml `
  --context 'https://github.com/gillissm/TheCodeAttic.ACRTask.SitecoreImages.git#sql' `
  --platform windows/amd64 `
  --commit-trigger-enabled true `
  --base-image-trigger-enabled true `
  --git-access-token <Personal_Access_Token>

az acr task create `
  -n SitecoreBaseImages-Headless `
  --registry thecodeatticimages `
  --file sc-base-headless.yml `
  --context 'https://github.com/gillissm/TheCodeAttic.ACRTask.SitecoreImages.git#headless' `
  --platform windows/amd64 `
  --commit-trigger-enabled true `
  --base-image-trigger-enabled true `
  --git-access-token <Personal_Access_Token>

az acr task create `
  -n SitecoreBaseImages-SQL-XM `
  --registry thecodeatticimages `
  --file sc-base-sql-xm.yml `
  --context 'https://github.com/gillissm/TheCodeAttic.ACRTask.SitecoreImages.git#sql-xm' `
  --platform windows/amd64 `
  --commit-trigger-enabled true `
  --base-image-trigger-enabled true `
  --git-access-token <Personal_Access_Token>
```
