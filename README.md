# DCPI Monthly Dashboard

This repository is the public/static dashboard artifact for the DCPI monthly update.

It intentionally contains only the shareable dashboard files:

- `index.html`
- `dashboard_snapshot.json`
- `export_manifest.json`

Raw CEX files and local intermediate analysis files should stay in the main DCPI project folder, not in this hosted dashboard repository.

## Refresh From The Local DCPI Project

From the main DCPI project folder:

```powershell
.\scripts\refresh_export_and_push_dashboard.ps1 -RemoteUrl "https://github.com/consumermacro-bit/wage_growth.git"
```

Use this after your local GitHub authentication is already set up. Do not paste GitHub passwords or personal access tokens into chat.

If CPI and Atlanta Fed WGT files have already been refreshed locally and you only want to rebuild from local inputs:

```powershell
.\scripts\refresh_export_and_push_dashboard.ps1 -SkipDownloads -RemoteUrl "https://github.com/consumermacro-bit/wage_growth.git"
```

## GitHub Pages

The included workflow deploys this folder as a static GitHub Pages site whenever `main` is pushed.

In GitHub, enable Pages with:

- Source: GitHub Actions

## Vercel

You can also import this repository into Vercel. The site is static and does not need a build command.

Suggested Vercel settings:

- Framework preset: Other
- Build command: leave blank
- Output directory: `.`
