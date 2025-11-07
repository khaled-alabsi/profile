# GitHub Pages Setup with GitHub Actions

This repository is configured to automatically deploy to GitHub Pages using GitHub Actions.

## 🚀 Quick Setup

### Step 1: Enable GitHub Pages with Actions

1. Go to your repository on GitHub: `https://github.com/khaled-alabsi/profile`
2. Click on **Settings** (top menu)
3. In the left sidebar, click **Pages**
4. Under **Source**, select **"GitHub Actions"** (not "Deploy from a branch")
5. Save the changes

### Step 2: Configure Custom Domain (Optional)

If you want to use a custom domain like `www.alabsi.space`:

1. In the same **Pages** settings page
2. Under **Custom domain**, enter your domain: `www.alabsi.space`
3. Click **Save**
4. Add a CNAME file to the repository root:
   ```bash
   echo "www.alabsi.space" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```
5. Configure your DNS provider:
   - For `www.alabsi.space`: Add a CNAME record pointing to `khaled-alabsi.github.io`
   - For apex domain (`alabsi.space`): Add A records pointing to:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```

## 📦 How It Works

The workflow (`.github/workflows/deploy.yml`) automatically:

1. **Triggers** on every push to the `main` branch
2. **Installs** Node.js and dependencies
3. **Generates** article content using the generate-articles script
4. **Builds** the Next.js application as static files
5. **Deploys** to GitHub Pages automatically

## 🔧 Manual Deployment

You can also trigger a deployment manually:

1. Go to **Actions** tab in your repository
2. Click on **Deploy to GitHub Pages** workflow
3. Click **Run workflow** button
4. Select the `main` branch
5. Click **Run workflow**

## 🌐 Accessing Your Site

After deployment (takes 1-2 minutes), your site will be available at:

- **With custom domain**: `https://www.alabsi.space`
- **Without custom domain**: `https://khaled-alabsi.github.io/profile`

## 📝 Development Workflow

### Local Development
```bash
npm run dev
# Visit http://localhost:3000
```

### Test Local Build
```bash
npm run test-local
npm run serve-local
# Visit http://localhost:8000
```

### Deploy to Production
Simply push to the `main` branch:
```bash
git add .
git commit -m "Your changes"
git push origin main
```

GitHub Actions will automatically build and deploy!

## 🔍 Monitoring Deployments

1. Go to the **Actions** tab in your repository
2. Click on the latest workflow run
3. Monitor the build and deployment progress
4. If there are errors, check the logs for details

## 🛠️ Troubleshooting

### Build Fails
- Check the Actions logs for specific errors
- Ensure all dependencies are in `package.json`
- Verify the build works locally: `npm run build`

### Site Not Updating
- Check that GitHub Pages source is set to "GitHub Actions"
- Wait 1-2 minutes after deployment completes
- Clear your browser cache (Ctrl+Shift+R or Cmd+Shift+R)

### 404 Errors
- Ensure GitHub Pages is properly configured
- Check that the workflow completed successfully
- Verify the deployment in the Actions tab

### Custom Domain Issues
- Verify DNS records are correctly configured
- Check the CNAME file exists in your repository
- Wait up to 24 hours for DNS propagation

## 📋 Configuration Files

- **`.github/workflows/deploy.yml`**: GitHub Actions workflow
- **`next.config.js`**: Next.js configuration for static export
- **`package.json`**: Build scripts and dependencies
- **`CNAME`** (optional): Custom domain configuration

## 🔒 Required Permissions

The workflow needs these permissions (already configured):
- `contents: read` - Read repository contents
- `pages: write` - Deploy to GitHub Pages
- `id-token: write` - Authentication for deployment

## 📚 Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Actions for Pages](https://github.com/actions/deploy-pages)
- [Next.js Static Export](https://nextjs.org/docs/app/building-your-application/deploying/static-exports)
- [Custom Domains Guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

## 🎯 Next Steps

1. ✅ Push this configuration to the `main` branch
2. ✅ Configure GitHub Pages to use GitHub Actions
3. ✅ (Optional) Set up custom domain
4. ✅ Make your first push to trigger deployment
5. ✅ Monitor the Actions tab for deployment status

---

**Note**: The old manual deployment script (`scripts/deploy-to-github-pages.sh`) is no longer needed with GitHub Actions, but is kept for reference or manual deployments if needed.
