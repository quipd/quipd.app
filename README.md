# Quipd Marketing Site

Static site for **quipd.app**. Hosted on GitHub Pages.

## Files

| File | Purpose |
|---|---|
| `index.html` | Landing page + live today's word + share link resolver |
| `privacy.html` | Privacy policy (linked from App Store Connect) |
| `terms.html` | Terms of use (linked from App Store Connect) |
| `404.html` | Custom 404 page ("Lost for words.") |
| `og-image.png` | Open Graph image for social sharing (1200x630) |
| `CNAME` | Custom domain config for GitHub Pages |
| `icons/` | Favicon and Apple touch icon |

## Deploying to GitHub Pages

1. Create a repo: `github.com/yourname/quipd-site`
2. Push all files to the `main` branch
3. Go to Settings → Pages → Source: "Deploy from a branch" → Branch: `main` → `/` (root)
4. Add your custom domain: `quipd.app`
5. In your domain registrar, add DNS records:
   - A records pointing to GitHub's IPs (185.199.108-111.153)
   - CNAME record: `www` → `yourname.github.io`
6. Wait for HTTPS to be provisioned (required for .app domains)

## Enabling CloudKit JS

The landing page includes CloudKit JS integration code (commented out in `index.html`). To enable live data:

1. Go to CloudKit Dashboard → API Access → create an API token
2. Set the allowed origin to `https://quipd.app`
3. Replace `YOUR_CLOUDKIT_API_TOKEN` in `index.html` with your token
4. Replace `iCloud.com.yourname.quipd` with your actual container ID
5. Uncomment the `fetchLiveData()` function body
6. The site will now show today's actual word and top responses

Until CloudKit is configured, the site shows fallback/demo data.

## Share link resolver

When users share quips from the app, the link format is:
```
https://quipd.app/?word=hidden&text=The+hidden+door+opened+both+ways&hearts=203
```

The `index.html` JavaScript parses these parameters and shows a modal with the shared quip + download CTA. No server needed.

## Updating content

The "How it works" section and chain display are static HTML. Update them directly. The "Today's word" showcase section will auto-update via CloudKit JS once enabled.
