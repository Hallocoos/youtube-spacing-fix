# Fix YouTube Video Gaps (Tampermonkey Script)

This guide will help you fix random gaps between YouTube videos caused by the `is-in-first-column` attribute using a Tampermonkey script.

## 🚀 How It Works

YouTube applies extra margin to certain video elements in the first column. This script **removes the attribute** to fix the layout.

## 🛠️ Installation Steps

### 1️⃣ Install Tampermonkey

If you haven’t installed it yet, download Tampermonkey for your browser:

- Stop Using [Google Chrome](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en)
- [Mozilla Firefox](https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/)
- [Microsoft Edge](https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpaadaobahmlepeloendndfphd)

### 2️⃣ Create a New Script

1. Click on the Tampermonkey extension icon.
2. Select **"Create a new script"**.
3. Delete the default template and paste the following code:

```js
// ==UserScript==
// @name         Remove YouTube is-in-first-column
// @namespace    http://tampermonkey.net/
// @version      1.0
// @description  Removes the is-in-first-column attribute on YouTube
// @author       You
// @match        *://www.youtube.com/*
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    function fixMargins() {
        document.querySelectorAll('ytd-rich-item-renderer[is-in-first-column]').forEach(el => {
            el.removeAttribute('is-in-first-column');
        });
    }

    // Run on page load and when navigating within YouTube
    new MutationObserver(fixMargins).observe(document.body, { childList: true, subtree: true });
    fixMargins();
})();

```

### 3️⃣ Save & Enable the Script

- Click **File > Save** or press `Ctrl + S`.
- Ensure the script is **enabled** in the Tampermonkey dashboard.

### 4️⃣ Refresh YouTube

Reload YouTube, and the random gaps should be gone! 🎉


## 🎯 Troubleshooting

- **Still seeing gaps?** Try disabling other extensions that modify YouTube.
- **Not working?** Ensure Tampermonkey is enabled and the script is active.
- **New YouTube updates?** If YouTube changes its structure, this script may need updates.

## 🔥 Enjoy Your Clean YouTube Layout!

No more annoying gaps—just a smooth, evenly spaced video grid! 🚀

## README.md generated with ChatGPT
