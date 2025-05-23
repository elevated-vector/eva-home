# Deployment Procedures for Elevated Vector Automation Website

This document outlines the deployment process for the Elevated Vector Automation website, which is hosted on GitHub Pages.

## Table of Contents

- [Overview](#overview)
- [Primary Deployment Method: GitHub Pages with GitHub Actions](#primary-deployment-method-github-pages-with-github-actions)
  - [Automatic Deployment](#automatic-deployment)
  - [Branching Strategy](#branching-strategy)
- [Manual Deployment Steps (If Needed)](#manual-deployment-steps-if-needed)
- [Custom Domain Configuration](#custom-domain-configuration)
  - [CNAME File](#cname-file)
  - [DNS Configuration](#dns-configuration)
- [SSL/TLS Certificates](#ssltls-certificates)
- [Pre-Deployment Checklist](#pre-deployment-checklist)
- [Post-Deployment Checks](#post-deployment-checks)
- [Troubleshooting Common Issues](#troubleshooting-common-issues)

## Overview

The website is designed for a zero-build process, utilizing pure HTML, CSS, and vanilla JavaScript. Deployment is primarily handled automatically via GitHub Actions when changes are pushed to the `main` branch.

- **Production URL**: [https://elevatedvector.com](https://elevatedvector.com)
- **Development URL (GitHub Pages default)**: [https://elevatedvector.github.io/elevatedvector.com/](https://elevatedvector.github.io/elevatedvector.com/)

## Primary Deployment Method: GitHub Pages with GitHub Actions

### Automatic Deployment

The repository is configured to use GitHub Actions for continuous deployment.

- **Trigger**: A push to the `main` branch.
- **Action**: The GitHub Pages workflow (typically `pages-build-deployment`) automatically builds (if necessary, though this project aims for zero-build) and deploys the site.
- **Process**:
  1. Changes are pushed to the `main` branch.
  2. GitHub Actions detects the push and triggers the deployment workflow.
  3. The workflow prepares the files and deploys them to the `gh-pages` branch (or serves directly from `main` if configured that way).
  4. GitHub Pages serves the updated content.
- **Deployment Time**: Typically takes 1-5 minutes for changes to go live.
- **Status**: You can monitor the status of deployments in the "Actions" tab of the GitHub repository. The GitHub Pages deployment badge in the `README.md` also reflects the latest status.

### Branching Strategy

- `main`: This is the primary branch for production-ready code. All deployments to the live site are made from this branch.
- Feature Branches (e.g., `feature/new-section`, `fix/bug-fix`): All development work should be done on separate feature branches. Once work is complete and tested, create a Pull Request to merge into `main`.

## Manual Deployment Steps (If Needed)

While automatic deployment is preferred, if manual intervention is ever required:

1. Ensure your local `main` branch is up-to-date with the remote repository.
2. Make any necessary changes directly or merge them into your local `main` branch.
3. Thoroughly test all changes locally.
4. Commit the changes:

    ```bash
    git add .
    git commit -m "deploy: manual update for critical fix"
    ```

5. Push the changes to the `main` branch on GitHub:

    ```bash
    git push origin main
    ```

6. GitHub Actions should then pick up these changes and deploy automatically. If GitHub Actions is disabled or failing, you might need to configure GitHub Pages settings directly in the repository (`Settings` > `Pages`).

## Custom Domain Configuration

The website uses the custom domain `elevatedvector.com`.

### CNAME File

A `CNAME` file must exist in the root of the repository.

- **Content**: It should contain a single line with the custom domain:

  ```curl
  elevatedvector.com
  ```

- This file tells GitHub Pages which custom domain to use.

### DNS Configuration

Your DNS provider (e.g., Cloudflare, as mentioned in the `README.md`) must be configured to point your custom domain to GitHub Pages. Typically, this involves:

- For an apex domain (e.g., `elevatedvector.com`):
  - `A` records pointing to GitHub Pages IP addresses:
    - `185.199.108.153`
    - `185.199.109.153`
    - `185.199.110.153`
    - `185.199.111.153`
- For a `www` subdomain (e.g., `www.elevatedvector.com`):
  - A `CNAME` record pointing to `YOUR_USERNAME.github.io` (e.g., `elevatedvector.github.io`).
- Consult GitHub's official documentation for the most up-to-date IP addresses and DNS configuration details.

## SSL/TLS Certificates

GitHub Pages automatically provides and renews SSL/TLS certificates for custom domains via Let's Encrypt.

- **Provisioning Time**: It can take up to 24-48 hours for the initial SSL certificate to be provisioned after configuring a custom domain.
- **Enforce HTTPS**: Ensure "Enforce HTTPS" is checked in your repository's GitHub Pages settings.

## Pre-Deployment Checklist

Before merging changes to `main` or initiating a deployment:

- [ ] **Code Validation**: Validate HTML and CSS (e.g., using W3C validators).
- [ ] **Linting**: Ensure code passes any linting checks (if linters are configured).
- [ ] **Local Testing**:
  - [ ] Test all new features and changes thoroughly.
  - [ ] Perform cross-browser testing (Chrome, Firefox, Safari, Edge).
  - [ ] Check mobile responsiveness across various screen sizes.
  - [ ] Verify accessibility (keyboard navigation, screen reader compatibility).
- [ ] **Performance Audit**: Run Lighthouse or similar tools to ensure performance metrics are met (target 90+).
- [ ] **Asset Optimization**: Ensure images and other assets are optimized for the web.
- [ ] **Link Checking**: Verify all internal and external links are working.
- [ ] **Review `README.md`**: Ensure any relevant changes to features or setup are documented.
- [ ] **Confirm Branch**: Ensure you are on the correct branch for deployment (`main`).

## Post-Deployment Checks

After a deployment is live:

- [ ] **Verify Production URL**: Open [https://elevatedvector.com](https://elevatedvector.com) and check that the latest changes are visible.
- [ ] **Hard Refresh/Clear Cache**: Perform a hard refresh (Ctrl+Shift+R or Cmd+Shift+R) or clear your browser cache to ensure you're not seeing a cached version.
- [ ] **Key Functionality Test**: Quickly test critical features and pages.
- [ ] **Check Console for Errors**: Open the browser's developer console to check for any new JavaScript errors or loading issues.
- [ ] **Monitor GitHub Actions**: Confirm the deployment workflow completed successfully in the "Actions" tab.

## Troubleshooting Common Issues

- **Changes Not Appearing**:
  - Check browser cache.
  - Verify the GitHub Actions deployment completed successfully.
  - Ensure you pushed to the correct branch (`main`).
  - Allow a few minutes for GitHub Pages to update.
- **Custom Domain Not Working**:
  - Double-check `CNAME` file content and location.
  - Verify DNS settings with your domain registrar/provider. DNS changes can take time to propagate.
  - Check GitHub Pages settings for any error messages related to the custom domain.
- **SSL Certificate Issues**:
  - Ensure "Enforce HTTPS" is enabled.
  - If newly configured, wait for the certificate to provision.
  - Check GitHub's status page for any ongoing issues.

For further assistance, refer to the [official GitHub Pages documentation](https://docs.github.com/en/pages).
