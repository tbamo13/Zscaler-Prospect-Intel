# HC Cyber Intel — PWA Deployment Guide

## Quick Setup for timzscaler.com (GitHub Pages)

### 1. Get your Anthropic API Key
- Go to https://console.anthropic.com
- Create an API key (you'll need the web search feature enabled)
- The app will ask for this key on first launch and stores it locally on your device

### 2. Push files to your GitHub repo
In your `timzscaler.com` repo (or whatever repo is behind your GitHub Pages):

```
your-repo/
├── hc-cyber-intel/
│   ├── index.html       ← main app
│   ├── manifest.json    ← PWA config
│   ├── sw.js            ← service worker
│   ├── icon-192.png     ← app icon
│   └── icon-512.png     ← app icon
```

Upload all 5 files into a folder called `hc-cyber-intel` in your repo.

### 3. Install on Android
1. Open Chrome on your phone
2. Go to `https://timzscaler.com/hc-cyber-intel/`
3. Chrome will show an "Add to Home Screen" banner, OR
4. Tap the three-dot menu → "Install app" or "Add to Home Screen"
5. The app will appear on your home screen like a native app

### 4. First Launch
- Enter your Anthropic API key when prompted
- Tap "Run Full Intelligence Scan"
- The app searches 5 intelligence categories with live web data

## What It Does
- **Healthcare Breaches**: Latest hospital/health system data breach incidents
- **Critical CVEs**: High-severity vulnerabilities in healthcare/medical devices
- **HIPAA & Regulations**: HHS/OCR rule changes, compliance updates
- **Threat Intelligence**: Ransomware campaigns targeting healthcare
- **Zscaler & Zero Trust**: Competitive intel on ZTNA/SSE/SASE in healthcare

Every item includes a **Zscaler Angle** — a ready-made talking point mapping the intel to ZIA, ZPA, ZDX, or Zero Trust for your prospect conversations.

## API Cost
Each full scan makes ~5 API calls with web search. Typical cost is roughly $0.10-0.20 per full scan depending on response length.
