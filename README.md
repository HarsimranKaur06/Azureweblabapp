Azure PHP Web App with GitHub Continuous Deployment
This project demonstrates how to deploy a PHP application to Azure App Service with automatic deployments via GitHub integration.

Quick Start Guide
1. Create Azure PHP Web App
Go to Azure Portal

Create a new Web App resource

Configure with:

Runtime stack: PHP (latest stable version)

Operating System: Linux (recommended)

Region: Choose nearest to your users

App Service Plan: Standard (S1)

2. Set Up Continuous Deployment from GitHub
In your Azure Web App:

Go to Deployment Center

Select GitHub as source

Authorize your GitHub account

Choose:

Organization: Your GitHub account/organization

Repository: Your PHP app repository (create new if needed)

Branch: main (or your preferred branch)

Click Save

Azure will automatically:

Create a GitHub Actions workflow file (.github/workflows/main_<your-app-name>.yml)

Set up deployment secrets in your repository

3. Connect Local Repository
Clone your GitHub repository locally:

bash
Copy
git clone https://github.com/your-username/your-repo.git
cd your-repo
Add your PHP application files:

bash
Copy
# Example for a simple PHP app
echo "<?php echo 'Hello Azure!'; ?>" > index.php
Commit and push your code:

bash
Copy
git add .
git commit -m "Initial PHP application"
git push origin main
4. Verify Deployment
Check GitHub Actions:

Go to your repository > Actions tab

You should see a running workflow named "Azure Web App"

Access your live application:

URL: https://<your-app-name>.azurewebsites.net

Changes should be live within 2-3 minutes after push

How It Works
The automatically generated workflow file:

Triggers on pushes to the main branch

Deploys directly to your Azure Web App

Uses the publish profile credentials stored in GitHub secrets

Local Development Tips
Run a local PHP server:

bash
Copy
php -S localhost:8000
Access at http://localhost:8000

Troubleshooting
Deployment fails: Check the workflow logs in GitHub Actions

Changes not appearing:

Verify the workflow completed successfully

Check Azure Web App > Deployment Center for errors

Clear browser cache when testing changes

Need to restart deployment: Push an empty commit:

bash
Copy
git commit --allow-empty -m "Trigger deployment"
git push
