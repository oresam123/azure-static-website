# Deployment Steps

These steps were completed manually via the Azure Portal.

## 1. Create a Resource Group
- Go to Azure Portal → Resource Groups → Create
- Name: choose a name
- Region: choose a region 

## 2. Create a Storage Account
- Go to Storage Accounts → Create
- Use the resource group created in 1
- use the same region as the resource group
- Redundancy: Locally Redundant Storage (LRS) — lowest cost option
- Leave all other settings as default

## 3. Enable Anonymous Blob Access
- Open the Storage Account
- Go to Settings → Configuration
- Set **Allow Blob anonymous access** to Enabled
- Click Save

> **Note:** Azure disables public blob access by default as a security measure.
> This must be enabled before static website hosting will work.
> In a production environment, access policies should be reviewed carefully.

## 4. Enable Static Website Hosting
- Open the Storage Account
- Go to Data Management → Static Website → Enable
- Index document: index.html
- Error document: 404.html
- Copy the Primary Endpoint URL — this is your live site

## 5. Upload Files
- Navigate to Containers → $web
- Upload index.html and 404.html

## 6. Verify Live Site
- Paste the Primary Endpoint URL into your browser
- Confirm index.html loads correctly
- Test the 404 page by adding a random path e.g. /test
