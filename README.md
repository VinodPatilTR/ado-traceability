# ado-traceability

Static HTML page for ADO traceability.

## Deploy on GitHub Pages

This repository is configured to deploy automatically with GitHub Actions.

### How it works

- Push changes to `main`.
- The workflow in `.github/workflows/deploy-pages.yml` publishes the site.
- GitHub Pages serves the app from the repository Pages URL.

### Entry page

- `index.html` redirects to `ADO_Traceability_Fixed_15.html`.
- Your app remains in `ADO_Traceability_Fixed_15.html`.

### Enable Pages once in GitHub UI

1. Open repository settings.
2. Go to **Pages**.
3. Under **Build and deployment**, choose **Source: GitHub Actions**.

After the first successful workflow run, your site will be available at:

`https://<your-github-username>.github.io/ado-traceability/`

## Custom domain setup

Your example `https://ADOTraceability_Tool` will not work as a GitHub Pages custom domain because:

- It has no top-level domain (for example `.com`).
- It contains an underscore (`_`), which is not valid in standard hostnames.

Use a valid domain instead, for example:

- `adotraceability-tool.com` (apex/root)
- `www.adotraceability-tool.com` (subdomain)

### 1. Configure DNS

For apex/root domain (`adotraceability-tool.com`), add these `A` records:

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

For `www` subdomain, add this `CNAME` record:

- `www` -> `vinodpatiltr.github.io`

### 2. Set the custom domain in GitHub

1. Open repository **Settings** -> **Pages**.
2. In **Custom domain**, enter your chosen domain.
3. Save and enable **Enforce HTTPS** after certificate provisioning is complete.

### 3. Commit a CNAME file (recommended)

Create a `CNAME` file in the repository root with exactly one line containing your domain, for example:

`www.adotraceability-tool.com`

This keeps the custom domain persistent across deployments.
