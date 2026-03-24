# josemiguelalves.dev

Static site for [AWS CLI Configure](https://github.com/josemiguelalves/aws-cli-configure-ext), published via GitHub Pages. The install section links to the [Open VSX listing](https://open-vsx.org/extension/josemiguelalves/aws-cli-configure-ext) for Cursor and other Open VSX&ndash;based editors.

## Create the GitHub repository (first time)

From this directory:

```bash
git init
git add index.html CNAME README.md
git commit -m "Initial site: AWS CLI Configure landing page"
```

Create a new **public** repository on GitHub (e.g. `josemiguelalves.dev`), then:

```bash
git remote add origin https://github.com/<your-username>/josemiguelalves.dev.git
git branch -M main
git push -u origin main
```

Or with GitHub CLI: `gh repo create josemiguelalves.dev --public --source=. --remote=origin --push`

## Enable GitHub Pages

1. Repo **Settings** &rarr; **Pages**.
2. **Build and deployment**: Source **Deploy from a branch**, branch **main**, folder **/ (root)**.
3. **Custom domain**: enter `josemiguelalves.dev`, save. Wait for DNS check; enable **Enforce HTTPS** when available.

The `CNAME` file in this repo tells Pages which hostname to serve.

## DNS (`josemiguelalves.dev`)

At your registrar or DNS host, use **either** apex **or** `www` as canonical (pick one; redirect the other in GitHub Pages if you add both).

### Apex (`josemiguelalves.dev`)

Add **A** records pointing to GitHub Pages (see [GitHub docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain)):

| Type | Host | Value |
|------|------|--------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

Optional **AAAA** for IPv6 (same doc lists the `2606:50c0:8000::153` &ndash; `8003` addresses).

### Subdomain (`www`)

| Type | Host | Value |
|------|------|--------|
| CNAME | `www` | `<your-username>.github.io` |

If the site repo is a **project** site (`username.github.io/repo`), the CNAME target is `username.github.io` and the custom domain is still set in Pages settings; follow GitHub&rsquo;s project Pages custom domain guide.

After DNS propagates, confirm **Enforce HTTPS** in Pages settings.
