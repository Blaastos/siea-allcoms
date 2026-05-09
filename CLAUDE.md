# siea-allcoms — Claude Code Project Guide

## Project Overview

PWA for Allcoms Technologies fiber optic field technicians. Runs offline-first on mobile devices (iOS/Android) installed via browser "Add to Home Screen". Deployed via GitHub Pages.

## Architecture

- **Framework**: React 18 (CDN, no build step)
- **Styling**: Inline CSS-in-JS (zero dependencies)
- **Persistence**: `localStorage` only (all data stays on device)
- **Offline**: Service Worker (`sw.js`) with cache-first strategy
- **PDF export**: `html2pdf.js` (CDN)
- **Signatures**: Canvas API (touch/finger drawing)

## Key Files

| File | Purpose |
|------|---------|
| `index.html` | Main app (all 4 modules integrated, ~585KB) |
| `allcoms_ftth_app_v3.html` | Mirror of index.html |
| `cr_allcoms.html` | Intervention completion report (CR) |
| `devis_fibre.html` | Maintenance quotation with pricing packages |
| `fiche_intervention.html` | EDL / technical reference sheet |
| `pv_expertise.html` | FTTH expertise/audit report |
| `sw.js` | Service Worker — update cache version here on each release |
| `manifest.json` | PWA manifest (name, icons, theme) |

## Development Workflow

No build tooling. Edit HTML files directly. All JS is vanilla React loaded from CDN.

### Making Changes
1. Edit the relevant `.html` file
2. If adding new assets, update the cache list in `sw.js`
3. Increment the cache version in `sw.js` (`ftth-terrain-v2` → `ftth-terrain-v3` etc.) so users get the update

### Testing
Open files directly in a browser or use a simple local server:
```bash
python3 -m http.server 8080
```
Then visit `http://localhost:8080`.

### Deployment
Push to `main` branch — GitHub Pages serves automatically from the root.

## Module Structure

Each HTML module is a self-contained single-file app with:
- React component tree
- PDF generation logic
- Canvas signature pad
- Form state in `localStorage`
- Print/export button

## Important Notes

- All HTML files are large (40–585KB), some with very long lines (minified sections)
- Language: French (UI, labels, PDF content)
- The app targets mobile-first; test layout at 390×844px (iPhone 14 viewport)
- No backend — everything runs client-side
