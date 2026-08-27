# Tab Out

**Keep tabs on your tabs.**

Tab Out is a Chrome extension that replaces your new tab page with a dashboard of everything you have open. Tabs are grouped by domain, with homepages (Gmail, X, LinkedIn, etc.) pulled into their own group. It also includes a Google search bar and custom shortcut bookmarks for the new-tab space.

No server. No account. Your saved tabs and shortcuts stay in Chrome storage.

---

## Install with a coding agent

Send your coding agent (Claude Code, Codex, etc.) this repo and say **"install this"**:

```
https://github.com/PatrickTangwen/tab-out
```

The agent will walk you through it. Takes about 1 minute.

---

## Features

- **See all your tabs at a glance** on a clean grid, grouped by domain
- **Search Google** from the top of the new-tab page
- **Custom shortcut bookmarks** with circular favicon tiles
- **Homepages group** pulls Gmail inbox, X home, YouTube, LinkedIn, GitHub homepages into one card
- **Close tabs with style** with swoosh sound + confetti burst
- **Duplicate detection** flags when you have the same page open twice, with one-click cleanup
- **Tab Out duplicate cleanup** only appears when more than one Tab Out page is open, and keeps the current page
- **Click any tab to jump to it** across windows, no new tab opened
- **Save for later** bookmark tabs to a checklist before closing them
- **Localhost grouping** shows port numbers next to each tab so you can tell your vibe coding projects apart
- **Expandable groups** show the first 8 tabs with a clickable "+N more"
- **Local-first storage** saved tabs and shortcuts stay in Chrome storage
- **Pure Chrome extension** no server, no Node.js, no npm, no setup beyond loading the extension

---

## Manual Setup

**1. Clone the repo**

```bash
git clone https://github.com/PatrickTangwen/tab-out.git
```

**2. Load the Chrome extension**

1. Open Chrome and go to `chrome://extensions`
2. Enable **Developer mode** (top-right toggle)
3. Click **Load unpacked**
4. Navigate to the `extension/` folder inside the cloned repo and select it

**3. Open a new tab**

You'll see Tab Out.

---

## How it works

```
You open a new tab
  -> Tab Out shows your open tabs grouped by domain
  -> Homepages (Gmail, X, etc.) get their own group at the top
  -> Click any tab title to jump to it
  -> Close groups you're done with (swoosh + confetti)
  -> Save tabs for later before closing them
```

Everything runs inside the Chrome extension. There is no external server or account. Saved tabs and custom shortcuts are stored in `chrome.storage.local`; searches go to Google only when you submit the search form, and shortcut/tab favicons are loaded from Google's favicon service.

> **Implementation update (August 26, 2026):** Favicons now prefer Chrome's built-in favicon data. Open tabs first use the favicon reported by `chrome.tabs`; shortcuts and saved tabs use the Manifest V3 `/_favicon/` endpoint, with each site's standard `/favicon.ico` as a direct fallback. The extension no longer depends on Google's favicon service.

---

## Tech stack

| What | How |
|------|-----|
| Extension | Chrome Manifest V3 |
| Storage | chrome.storage.local |
| Sound | Web Audio API (synthesized, no files) |
| Animations | CSS transitions + JS confetti particles |

---

## License

MIT

---

Originally built by [Zara](https://x.com/zarazhangrui). Customized in this repo by [PatrickTangwen](https://github.com/PatrickTangwen).
