# HC Cyber Intel — Installation & Deployment Guide

A Progressive Web App (PWA) that delivers real-time healthcare cybersecurity intelligence with ready-made Zscaler sales talking points.

---

## Prerequisites

- A GitHub account with a GitHub Pages-enabled repository
- An Anthropic API key with web search access
- A modern browser (Chrome 80+, Safari 14+, Edge 80+)

---

## Step 1 — Get Your Anthropic API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign in or create an account
3. Navigate to **API Keys** → **Create Key**
4. Copy the key — it starts with `sk-ant-`
5. Ensure your account has **web search** enabled (required for live intelligence scans)

> **Cost estimate**: Each full scan makes ~5 API calls with web search. Typical cost is **$0.10–0.20 per full scan**.

---

## Step 2 — Deploy to GitHub Pages

### File structure

Place all 5 files into a folder named `hc-cyber-intel` in your repo:

```
your-repo/
└── hc-cyber-intel/
    ├── index.html       ← main application
    ├── manifest.json    ← PWA metadata
    ├── sw.js            ← service worker (offline support)
    ├── icon-192.png     ← app icon (small)
    └── icon-512.png     ← app icon (large)
```

### Push to GitHub

```bash
git add hc-cyber-intel/
git commit -m "Add HC Cyber Intel PWA"
git push origin main
```

### Enable GitHub Pages

1. Go to your repo on GitHub → **Settings** → **Pages**
2. Under **Source**, select `Deploy from a branch`
3. Choose `main` branch, `/ (root)` folder → **Save**
4. Your app will be live at `https://<your-username>.github.io/<repo-name>/hc-cyber-intel/`

If you use a custom domain (e.g. `timzscaler.com`), your URL will be:
`https://timzscaler.com/hc-cyber-intel/`

---

## Step 3 — Install as a PWA

### Android (Chrome) — Recommended

1. Open **Chrome** on your Android device
2. Navigate to your deployment URL
3. Chrome will show an **"Add to Home Screen"** banner at the bottom — tap **Add**
   - If the banner doesn't appear: tap the **three-dot menu (⋮)** → **"Install app"** or **"Add to Home Screen"**
4. The app installs to your home screen and launches like a native app (no browser chrome)

### iPhone / iPad (Safari)

1. Open **Safari** on your iOS device (must be Safari — Chrome on iOS cannot install PWAs)
2. Navigate to your deployment URL
3. Tap the **Share button** (box with arrow at the bottom of the screen)
4. Scroll down and tap **"Add to Home Screen"**
5. Edit the name if desired → tap **Add**
6. The app appears on your home screen

### Desktop (Chrome / Edge)

1. Navigate to your deployment URL in Chrome or Edge
2. Look for the **install icon** (⊕ or computer icon) in the address bar — click it
3. Click **Install** in the prompt
4. The app opens in its own window, separate from the browser

---

## Step 4 — First Launch

1. Open the app from your home screen
2. Enter your Anthropic API key when prompted (`sk-ant-...`)
   - Your key is stored **locally on your device only** — never sent anywhere except directly to the Anthropic API
   - Press **Enter** or tap **Activate Intelligence Feed**
3. Tap **▶ Run Full Intelligence Scan**
4. The app scans 5 intelligence categories sequentially — takes ~60–90 seconds

---

## Intelligence Categories

| Category | What It Covers |
|---|---|
| 🏥 Healthcare Breaches | Latest hospital and health system data breach incidents |
| 🛡️ Critical CVEs | High-severity vulnerabilities in healthcare and medical devices |
| ⚖️ HIPAA & Regulations | HHS/OCR rule changes and compliance updates |
| 🔍 Threat Intelligence | Ransomware campaigns and APT activity targeting healthcare |
| ⚡ Zscaler & Zero Trust | ZTNA/SSE/SASE competitive intel in healthcare |

Every item includes a **Zscaler Angle** — a ready-made talking point mapping the threat to ZIA, ZPA, ZDX, or Zero Trust.

---

## Managing Your API Key

- Tap the **⚙️ gear icon** (top right) to view or reset your API key
- Tap **Reset Key** to clear it and enter a new one
- The key is stored in browser `localStorage` under `hc_cyber_intel_api_key`

---

## Troubleshooting

| Issue | Fix |
|---|---|
| "Failed: API error" on scan | Check your API key is valid and has web search enabled |
| App won't install as PWA | Must be served over HTTPS (GitHub Pages provides this) |
| iOS install option missing | Must use Safari, not Chrome, on iPhone/iPad |
| Blank screen after install | Clear the app data and reload; service worker may have cached a stale version |
| Scan hangs indefinitely | Check network connection; each category scan can take 15–30 seconds |
