# rvn.consulting

Static site for rvn.consulting. Plain HTML and CSS, no build step.

## Files

- `index.html`: the whole site, one page
- `assets/style.css`: styles
- `assets/favicon.svg`, `assets/og.svg`: icon and social preview image
- `CNAME`: tells GitHub Pages to serve at rvn.consulting
- `.nojekyll`: skips Jekyll processing on GitHub Pages
- `404.html`, `robots.txt`, `sitemap.xml`

## Preview locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy to GitHub Pages

1. Create a repository on GitHub (public, any name, for example `rvn`).
2. Push this folder to the `main` branch.
3. In the repository, open Settings, then Pages. Under "Build and deployment" choose "Deploy from a branch", branch `main`, folder `/ (root)`.
4. Under "Custom domain" enter `rvn.consulting` and save. The `CNAME` file in this repo keeps that setting across deploys.
5. Tick "Enforce HTTPS" once the certificate is issued (usually within an hour of DNS resolving).

## DNS at your registrar

For the apex domain, add four A records pointing `rvn.consulting` at GitHub Pages:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Optionally add a CNAME record for `www` pointing to `<your-github-username>.github.io` so www redirects to the apex.

Check the current IPs in the GitHub Pages docs before adding them, in case they have changed.
