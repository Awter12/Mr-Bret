# Deployment Log — mr-bret.site

**Project:** Mr. Bret CV/Portfolio Website
**Repo:** https://github.com/awter12/Mr-Bret
**Live URL:** https://mr-bret.site
**Date:** August 2026

 Deploy on GitHub Pages

**Goal:** Go live on a GitHub-provided URL.

- Enabled GitHub Pages in repo Settings → Pages (branch: `main`, root)
- Site went live at: `https://awter12.github.io/Mr-Bret/`
- Verified the deployed site matched the local content


Custom Domain + Cloudflare

**Goal:** Point purchased domain (`mr-bret.site`, bought via GoDaddy) at the GitHub Pages site, fronted by Cloudflare for DNS/security.

— Added domain to Cloudflare
- Created Cloudflare account, added `mr-bret.site` as a site (Free plan)
- Cloudflare provided two nameservers

— Switched nameservers at GoDaddy
- Changed domain nameservers from GoDaddy defaults to Cloudflare's nameservers
- Propagation confirmed once Cloudflare showed the zone as **Active**

Certificate provisioning
- Set new DNS records to **DNS only** (grey cloud) temporarily
- Set custom domain `mr-bret.site` in repo Settings → Pages
- Waited for GitHub's "DNS check successful" + Let's Encrypt certificate issuance


Enabled Cloudflare proxy
- Switched `@` and `www` records back to **Proxied** (orange cloud)
- Set Cloudflare SSL/TLS mode to **Full (strict)** (avoids the Flexible-mode redirect loop issue)
- Purged Cloudflare cache (Caching → Configuration → Purge Everything)

**Result:** ✅ `https://mr-bret.site` now correctly serves the GitHub Pages CV site, proxied through Cloudflare with HTTPS enforced.