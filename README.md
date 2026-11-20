# Throttle website

The public website of Throttle: what it is, its terms of service and its privacy policy.
TikTok's and Meta's developer forms ask for these three addresses before an app can be saved, and
Google asks for them before the sign-in of an app can be made to last.

Plain static pages. There is no build step and nothing to install.

| Page | File | Address once it is online |
| --- | --- | --- |
| Front page | `index.html` | `https://p0six.github.io/throttle-web/` |
| Terms of service | `terms.html` | `https://p0six.github.io/throttle-web/terms.html` |
| Privacy policy | `privacy.html` | `https://p0six.github.io/throttle-web/privacy.html` |

`404.html` is what GitHub Pages shows for an address that does not exist. `assets/` holds the
stylesheet and the icon. `.nojekyll` tells GitHub Pages to serve the files as they are.

## Putting it online

1. Push `main` to GitHub.
2. On GitHub open the repository's **Settings**, then **Pages**. Under "Build and deployment" choose
   **Deploy from a branch**, branch **main**, folder **/ (root)**, and press **Save**.
3. About a minute later the site is online. The Pages settings show its exact address.

Every later push to `main` updates the site by itself.

## Where the addresses go

- **TikTok developer portal**, in the app's details: Website URL, Terms of Service URL, Privacy Policy URL.
- **Meta app dashboard**, under App settings, Basic: Privacy Policy URL and Terms of Service URL. If it asks
  for data deletion instructions, use `privacy.html#removing`.
- **Google Cloud console**, under Google Auth Platform, Branding: Application home page, Application
  privacy policy link, Application terms of service link. On the same page, under "Authorized domains",
  add the domain of these addresses (`p0six.github.io` for the addresses above). Google keeps
  "Publish app" on its Audience page grey until this page is filled in. Leave the logo empty there:
  with a logo, Google wants to verify the app first.

## Looking at it on your own computer

```
python3 -m http.server 8000
```

Then open `http://localhost:8000/`.

## Changing it

- The words are in the three `.html` files, the look is in `assets/site.css`.
- When the terms or the privacy policy change, change their "Last updated" date too.
- The privacy policy says that this site sets no cookies, has no analytics and loads nothing from other
  sites. Keep it true: each page carries a Content-Security-Policy that blocks anything from elsewhere.
- The links between pages are relative, so the site also works on a domain of its own.
