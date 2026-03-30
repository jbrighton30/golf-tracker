# Golf Tracker

A static webpage showing golf leaderboards and stats for our group.

**Repository:** https://github.com/jbrighton_expedia/golf-tracker

## Setup

### 1. Google Sheets — Share the sheet

Open your Google Sheet → Share → change to "Anyone with the link can view".

Copy the Sheet ID from the URL:
`https://docs.google.com/spreadsheets/d/`**`THIS_IS_YOUR_SHEET_ID`**`/edit`

### 2. Google Cloud — Create an API key

1. Go to https://console.cloud.google.com
2. Create a new project (or use an existing one)
3. Enable the **Google Sheets API**
4. Go to Credentials → Create Credentials → API key
5. Click "Restrict key":
   - Application restrictions → HTTP referrers → add your GitHub Pages URL: `https://YOUR_USERNAME.github.io/*`
   - API restrictions → Restrict to → Google Sheets API
6. Copy the key

### 3. Configure `index.html`

Open `index.html` and update the two constants near the top of the `<script>` block:

```js
const SHEET_ID = 'paste-your-sheet-id-here';
const API_KEY  = 'paste-your-api-key-here';
```

### 4. Deploy to GitHub Pages

1. Push this folder to a GitHub repo
2. Go to repo Settings → Pages
3. Set source to "Deploy from a branch" → `main` → `/ (root)` (or `/golf-tracker` if it's a subfolder)
4. Visit `https://YOUR_USERNAME.github.io/REPO_NAME`

## Keeping scores up to date

Edit the Google Sheet directly. The webpage fetches live data on every page load.
