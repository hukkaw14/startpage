# ~/startpage

> A terminal-aesthetic browser startpage with GitHub Gist sync, live weather, and customizable bookmarks.

[![Live Demo](https://img.shields.io/badge/demo-live-brightgreen?style=flat-square)](https://najmossalahin.github.io/startpage/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE)
[![HTML](https://img.shields.io/badge/html-71.9%25-orange?style=flat-square)](index.html)
[![CSS](https://img.shields.io/badge/css-28.1%25-blue?style=flat-square)](style.css)
[![No Dependencies](https://img.shields.io/badge/dependencies-none-success?style=flat-square)]()

![Startpage preview](startpage.gif)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
- [Setup](#setup)
- [GitHub Token Setup](#github-token-setup)
- [Usage](#usage)
- [Customization](#customization)
- [File Structure](#file-structure)
- [Design](#design)
- [Credits](#credits)
- [License](#license)

---

## Overview

`~/startpage` is a minimal, keyboard-driven browser start page built with vanilla HTML, CSS, and JavaScript — no frameworks, no build step, no dependencies. It stores your bookmarks in a private GitHub Gist so they sync across any device and browser.

The interface mimics a terminal prompt: type to search, press Enter to navigate, and use `Ctrl+R` to open a built-in CLI overlay.

---

## Features

| Feature | Description |
|---|---|
| **Keyboard Search** | Type anywhere to search via DuckDuckGo, or enter a URL to navigate directly |
| **GitHub Gist Sync** | Bookmarks are stored in a private Gist and synced across all your devices |
| **Categorized Bookmarks** | Organize links into named categories with pagination (5 links per page) |
| **Starred Links** | Mark important links as starred for quick visual identification |
| **CLI Overlay** | Press `Ctrl+R` to open a terminal-style command overlay |
| **Live Weather** | Real-time weather via Open-Meteo — set a city or auto-detect your location |
| **Clock** | Live clock with 12h/24h toggle (click the time to switch) |
| **GIF Switcher** | Cycle through custom GIFs; add via URL or upload a local file |
| **Quick-Access Links** | Three dot buttons (top-right) for your most-visited sites |
| **Offline Mode** | Falls back to a local cache when the network is unavailable |
| **Mobile Support** | Dedicated search input for mobile/touch devices |

---

## Demo

**[→ Live Preview](https://najmossalahin.github.io/startpage/)**

---

## Setup

No build step or package manager required. Three ways to use it:

### Option 1 — GitHub Pages (recommended)

1. Fork this repository.
2. Go to **Settings → Pages** and set the source to the `master` branch.
3. Your startpage will be live at `https://<your-username>.github.io/startpage/`.
4. Set that URL as your browser's homepage or new tab page.

### Option 2 — Clone and serve locally

```bash
git clone https://github.com/NajmosSalahin/startpage.git
cd startpage
# Open index.html in your browser, or serve with any static file server:
npx serve .
```

### Option 3 — Direct download

Download `index.html`, `style.css`, and `favicon.ico`, then open `index.html` as your browser's homepage.

---

## GitHub Token Setup

A GitHub Personal Access Token with the `gist` scope is required to sync your bookmarks. Your token is cached locally for 30 days.

1. Go to [github.com/settings/tokens/new](https://github.com/settings/tokens/new).
2. Give it a name (e.g. `startpage-sync`).
3. Under **Select scopes**, check **gist** only.
4. Click **Generate token** and copy it.
5. On first load, paste the token into the prompt and click **Connect & Sync**.

> **Note:** Your token is stored only in `localStorage` on your device and is never sent anywhere except the official GitHub API.

---

## Usage

### Search & Navigation

| Action | Behavior |
|---|---|
| Type any text | Begins a DuckDuckGo search query |
| Type a URL | Navigates directly to that URL |
| `Enter` | Submits the search or URL |
| `Backspace` | Deletes the last character |
| `Ctrl+R` | Opens / closes the CLI overlay |

### Weather Widget

- Click the weather bar to toggle between summary view and detail view (humidity, rain chance, feels-like temperature).
- Set your location in **Settings → Weather Location**, or click **Auto** to use device geolocation.
- Weather refreshes automatically every minute.

### Clock

- Click the date/time display to toggle between 12-hour and 24-hour format.

---

## Customization

Open the **Settings** panel (gear icon, top-left) to:

- **Add / edit / delete** bookmark categories and links.
- **Star** links to visually highlight them.
- **Set or change** your weather location.
- **Add GIFs** by URL or local file upload; cycle through them by clicking the GIF.
- **Configure quick-access dot buttons** (top-right corner links).

All changes are saved to your GitHub Gist on **Save Changes**.

To change the default bookmarks that appear for new users, edit the `DEFAULT_BOOKMARKS` array near the top of `index.html`.

---

## File Structure

```
startpage/
├── index.html       # Application — all logic is self-contained here
├── style.css        # Gruvbox Dark theme and layout
├── favicon.ico      # Browser tab icon
├── cat.gif          # Default GIF
├── startpage.gif    # README preview screenshot
└── LICENSE          # MIT License
```

---

## Design

| Property | Value |
|---|---|
| **Color Scheme** | [Gruvbox Dark](https://github.com/morhetz/gruvbox) |
| **Font** | [Fira Code](https://github.com/tonsky/FiraCode) |
| **Aesthetic** | Terminal / neovim-inspired |
| **Cat GIF Source** | [@avogado6 on Twitter](https://twitter.com/avogado6/status/1165595520967954432) |

---

## Credits

- Forked from [kencx/startpage](https://github.com/kencx/startpage)
- Weather data by [Open-Meteo](https://open-meteo.com/) (free, no API key required)
- Geocoding by [Nominatim / OpenStreetMap](https://nominatim.org/)

---

## License

MIT — see [LICENSE](LICENSE) for details.  
Feel free to fork and make it your own!
