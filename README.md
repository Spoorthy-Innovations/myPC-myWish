# myPC myRight ✂️📋🔒➡️🔓

myPC myRight is a Chrome extension that **forces paste and copy**, unlocks **text selection**, **right click**, and can **temporarily show password fields on hover/focus**, even on websites that try to block them. 🚀

## Features 🌟

- ✨ **Force paste**: lets you paste text into fields on sites that block `Ctrl+V` / `Cmd+V`.
- ⚡ **Force copy & cut**: blocks page handlers that try to stop `Ctrl+C` / `Cmd+X`.
- 🖱️ **Unlock selection**: overrides `user-select: none` and similar tricks so you can select text.
- 🧩 **Right click**: re‑enables the browser context menu when sites try to disable it.
- 👁️‍🗨️ **Show password on hover/focus**: when enabled, password fields temporarily show as plain text while you hover or edit, then hide again when you move away or blur.

Technically, myPC myRight injects a content script that runs at `document_start` and registers its own listeners in the **capture phase**, calling `stopImmediatePropagation()` to prevent the page from blocking normal browser behavior, without calling `preventDefault()` so the default copy/paste/select actions still occur. 🧠

## Install in Chrome (Public) 🆓

1. Open Chrome and go to `chrome://extensions/`.
2. Turn on **Developer mode** (top right).
3. Click **Load unpacked**.
4. Select this folder: `myPC-myRight` (the one containing `manifest.json`).
5. The extension will appear in your toolbar. You can pin it to see “myPC myRight by Spoorthy”.

## Install in Chrome (Pro) 💎

The **Pro version** lives under `src/pro` and ships as a separate extension called **“myPC myRight Pro”**.

1. Open Chrome and go to `chrome://extensions/`.
2. Turn on **Developer mode** (top right).
3. Click **Load unpacked**.
4. Select the `src/pro` folder (the one containing `manifest.json` for Pro).
5. You will see a second extension in the toolbar named **“myPC myRight Pro”** with a gold **Pro** badge in the popup.

## Usage (Public) 🖥️

- 💻 On any tab, use **Ctrl+V** (Windows/Linux) or **Cmd+V** (Mac) to paste, and **Ctrl+C** / **Cmd+C** to copy, even on sites that normally block it.
- 🧷 Click the extension icon to open the popup.
- 🎚️ Use the toggles to enable/disable:
  - ✅ **Copy**
  - ✅ **Paste**
  - ✅ **Selection**
  - ✅ **Right click**
  - ✅ **Show password on hover/focus**

## Usage (Pro) 💼

When you click the **myPC myRight Pro** icon you get all the free toggles plus two extra sections: **Advanced** and **Power Tools**. ⚙️

- ⚡ **Advanced**
  - 👀 **Visibility Bypass**: prevents sites from detecting tab switches using the Page Visibility API or blur/focus tricks.
  - ⌨️ **Keyboard Unblock**: unlocks F12, Ctrl+U, Ctrl+S, Ctrl+P, Ctrl+Shift+I/J/C so sites cannot cancel them.
  - 🧼 **Overlay Removal**: detects and neutralizes transparent, full‑page overlay layers that block clicks or selection.
  - 🖱️ **Drag & Drop**: re‑enables dragging text and images by undoing `ondragstart` and anti‑drag CSS.
  - 🖨️ **Print Unlock**: injects print CSS so pages cannot hide text when you print or save as PDF.

- 🛠️ **Power Tools**
  - 🧭 **Scroll Unlock**: forces scrollbars back on pages that lock scrolling (e.g., paywalls or full‑screen modals).
  - 🎬 **Video Controls**: forces native HTML5 video controls to appear and stay usable.
  - 🔐 **Autocomplete Enforcer**: removes `autocomplete="off"`/`new-password` so the browser can offer to save passwords.
  - 🚪 **Exit Dialog Bypass**: kills “Are you sure you want to leave?” beforeunload popups.
  - 🧨 **Element Zapper**: when enabled, **Alt+Shift+Click** instantly removes any element you click on.

## Why it’s generally OK ✅

- 🧱 **No remote code**: Everything runs locally; all JavaScript is packaged inside the extension. This follows Chrome Manifest V3 security requirements.
- 🔐 **Minimal permissions**:
  - 🌐 `content_scripts` on `<all_urls>` (needed so myPC myWIsh can work on any page).
  - 🪪 `activeTab`, `storage`. No host-permission abuse, no network access, no external APIs.
- 🕵️‍♀️ **No data collection**: The code never reads or sends passwords, cookies, browsing history, or any other personal data. It only adjusts browser behavior (events and CSS) to stop sites from blocking standard copy/paste/selection/right-click/password visibility.

## Status 🚀

Both **Public 🆓** and **Pro 💎** versions have been **submitted to the Chrome Web Store for review** ✅ and are currently **waiting to appear in the store listings** 🕒.

## Building and releasing 🏗️📦

See **BUILD.md** for detailed build & release steps (CLI commands, ZIP generation, and version bump checklist). 📝

## Privacy statement 🔒

- 🎯 **Single purpose (Public)**  
  myPC myRight *“allows users to force copy, paste, text selection, right click, and temporary password visibility on webpages that try to block them.”*

- 🎯 **Single purpose (Pro)**  
  myPC myRight Pro *“allows users to force copy, paste, selection, right-click, password visibility, and advanced controls (e.g. DevTools unlock, print, scroll, video controls, overlay removal) on webpages that try to block them.”*

- 🚫 **No data collection**  
  Both extensions *“do not collect, store, or transmit any personal or usage data. All processing happens locally in the browser.”*

- 👁️‍🗨️ **Password behavior**  
  When the password feature is enabled, it can **temporarily show password fields on hover/focus** so the user can see what they typed. Passwords are never sent anywhere; this behavior is intentional, user‑visible, and fully controlled by the user via the popup toggle.

Built by **Vasavya Yagati** at **Spoorthy Innovations**. 💚

## Contact 📬

- 👤 **Name**: Vasavya Yagati  
- 📧 **Email**: [vasavya@yagati.com](mailto:vasavya@yagati.com)  
- 🏢 **Company Email**: [info@spoorthy.org](mailto:info@spoorthy.org)  
- 🌐 **Website**: [http://spoorthy.org](http://spoorthy.org)  

This is the **first free product** from **Spoorthy Innovations and Research Foundation** (`spoorthy.org`). 🎉
