# OCodejs.dev domain and hosting plan

## Canonical domain

- Preferred public hostname: `https://ocodejs.dev`
- Optional canonical redirect: `https://www.ocodejs.dev` → `https://ocodejs.dev`
- Product/brand name: **OCode.js**
- Repository: [zskbot/js](https://github.com/zskbot/js)

## Current repository hosting evidence

The repository contains a GitHub Pages workflow at `.github/workflows/static.yml`. It deploys the repository root when a commit is pushed to `main`. The Vercel configuration also declares a Jekyll service, but this alone does not prove that a Vercel project is connected or deployed.

For that reason, this change documents the target domain only. It does not add a `CNAME` file, alter DNS, change GitHub Pages settings, create a Vercel project, or trigger a production deployment.

## Activation checklist

1. Register `ocodejs.dev` with a domain registrar, or confirm that the user already owns and controls it.
2. Verify the domain in the chosen hosting provider before changing DNS.
3. Choose one canonical hosting target. The repository currently has a GitHub Pages production workflow; use its official custom-domain instructions if GitHub Pages remains the host.
4. Configure the apex domain and optional `www` alias using the exact DNS records shown by the selected provider. Do not copy records from another project or guess IP addresses.
5. Enable HTTPS and wait for the provider's certificate issuance.
6. Verify the apex and `www` behavior, redirects, TLS certificate, and the site's key routes.
7. Only then add the provider-specific custom-domain file/configuration and merge the reviewed change.

## Safety and release policy

- Work on a feature branch and use a pull request.
- Do not push directly to `main`; its workflow deploys to GitHub Pages.
- Do not change DNS, registrar nameservers, production hosting, or project ownership without explicit authorization and verified account access.
- Never commit registrar credentials, DNS API tokens, or hosting secrets.
- A GitHub Preview URL or a successful CI build is not proof that `ocodejs.dev` is live.

## Verification record

| Check | Status |
|---|---|
| Target hostname selected | `ocodejs.dev` |
| Repository hosting workflow inspected | GitHub Pages deploys on pushes to `main` |
| Domain ownership/registration | Not verified |
| DNS records | Not configured |
| Custom domain attached to hosting | Not configured |
| HTTPS on custom domain | Not verified |
| Production deployment | Not performed |
