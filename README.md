# Azure PHP Web App with GitHub Continuous Deployment

This project demonstrates automatic deployment of a PHP application to Azure App Service using GitHub integration.

## 🚀 Quick Deployment Guide

### 1. Create Azure Web App
1. Go to [Azure Portal](https://portal.azure.com/)
2. Create new **Web App** resource
3. Configure:
   - **Runtime stack**: PHP (latest version)
   - **OS**: Linux (recommended)
   - **Region**: Nearest to your users
   - **Pricing tier**: Free (F1) for testing

### 2. Set Up GitHub Deployment
1. In your Azure Web App:
   - Navigate to **Deployment Center**
   - Select **GitHub** as source
   - Authorize your GitHub account
   - Configure:
     - Repository: Your PHP app repo (create new if needed)
     - Branch: `main`
   - Click **Save**

Azure will automatically:
- Create GitHub Actions workflow (`.github/workflows/main_<app-name>.yml`)
- Configure deployment secrets

### 3. Connect Local Code
```bash
# Clone your repository
git clone https://github.com/your-username/your-repo.git
cd your-repo

# Add PHP files
echo "<?php echo 'Hello Azure!'; ?>" > index.php

# Commit and push
git add .
git commit -m "Initial commit"
git push origin main
```

### 4. Verify Deployment

Check deployment status:

GitHub repo → Actions tab

Azure Portal → Deployment Center

Access live app:

Copy

https://<your-app-name>.azurewebsites.net



###  How It Works

Automatic deployments on every git push

GitHub Actions workflow handles deployment

Typical deployment time: 2-3 minutes

