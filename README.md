# ONE MART Outstanding App — GitHub Pages package

This repository hosts the installable app shell. The live retailer data and app interface remain in Google Apps Script.

## 1. Important: update Google Apps Script first

In your existing Apps Script project, replace only `doGet()` in `Code.gs` with:

```javascript
function doGet() {
  return HtmlService.createHtmlOutputFromFile('Index')
    .setTitle(APP_TITLE)
    .addMetaTag('viewport', 'width=device-width, initial-scale=1')
    .setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL);
}
```

Save, then Deploy → Manage deployments → Edit → New version → Deploy. Keep the web app access setting as intended for your team. The app is displaying financial information, so share its link only with authorized staff.

## 2. Upload these files to GitHub

Upload the contents of this folder to the root of the public repository `onemartch-sudo/one-mart-outstanding-app`:
- `index.html`
- `manifest.webmanifest`
- `sw.js`
- `icons/` folder
- `README.md`

Do not upload your private admin upload key or Google Sheet.

## 3. Enable GitHub Pages

In the repository, open Settings → Pages. Under Build and deployment choose:
- Source: Deploy from a branch
- Branch: `main`
- Folder: `/ (root)`
Then Save.

Your site address should be:
`https://onemartch-sudo.github.io/one-mart-outstanding-app/`

## 4. Install

- Android: open the site in Chrome → menu (⋮) → Install app or Add to Home screen.
- iPhone: open the site in Safari → Share → Add to Home Screen.

## Notes

- Internet access is required for live outstanding data and Excel uploads.
- The service worker caches only the app shell, not financial data.
- The Google Apps Script page must be redeployed with the iframe setting above before the GitHub Pages shell can display it.
- Test the published site and sign-in/access behavior before sharing it with the sales team.
