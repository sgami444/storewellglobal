# StoreWell Global

A compact coming soon page for https://storewellglobal.com. Plain HTML, CSS, and a small script that keeps the copyright year current. No build or dependencies required.

## Preview locally

From this folder, run:

```powershell
python -m http.server 4173 --bind 127.0.0.1 --directory public
```

Open http://127.0.0.1:4173. Stop the server with Ctrl+C.

## Update the page

Edit `public/index.html` for copy and contact links, `public/styles.css` for colors and layout, and `public/favicon.svg` for the browser icon. Keep the brand, tagline, email, and phone consistent. Contact buttons open the visitor's email or phone application; this site does not collect or store submissions.

## Publish with GitHub Pages

Repository: https://github.com/sgami444/storewellglobal

Default website address: https://sgami444.github.io/storewellglobal/

In repository **Settings → Pages**, set the source to **GitHub Actions**. The workflow in `.github/workflows/pages.yml` publishes only `public/` on every push to `main`, or when run manually from the Actions tab. No build command or dependencies are required.

## Connect the GoDaddy domain when ready

First verify the default GitHub Pages address works. In repository **Settings → Pages → Custom domain**, save `storewellglobal.com` before updating DNS. Then in GoDaddy's DNS manager:

| Type | Name | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | sgami444.github.io |

Replace only conflicting website records for `@` and `www`. Leave nameservers and all email records (MX, SPF, DKIM, DMARC, autodiscover) unchanged. The domain currently has email MX records. Check for conflicting apex AAAA records or domain forwarding before switching. Use GoDaddy's default TTL.

After DNS verifies and GitHub issues the certificate, enable **Enforce HTTPS**. Verify the root domain, the `www` redirect, assets, and contact links. GitHub handles the `www` redirect when both domain variants point to Pages. With this Actions workflow, the custom domain is configured in GitHub settings; a source `CNAME` file is not required.

Only `public/` is published. There is no confirmed launch date or operating location. Domain setup and mailbox delivery are independent of the local page.

Official setup references: [GitHub Pages publishing](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) and [custom domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).
