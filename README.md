# TheCodeAttic.ACRTask.SitecoreImages

Files to Support ACR Task to automate Sitecore Image builds.

## Task Create Scripts

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
```