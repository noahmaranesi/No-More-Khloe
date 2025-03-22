# No More Khloe
Hide the annoying “Khloé in Wonder Land” in the sidebar on [X.com](https://x.com) & [Twitter.com](https://twitter.com).

<img width="750" src="https://github.com/user-attachments/assets/752d82e8-ee13-4b79-85ea-c1421095284c" />


### Installation

Requires an extension/app that allows userscript and Javascript modifications to websites, such as [Tampermonkey for Chrome](https://chromewebstore.google.com/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo) (Free), [Tampermonkey for Firefox](https://addons.mozilla.org/firefox/addon/tampermonkey) (Free), or [Userscripts for Safari](https://apps.apple.com/app/userscripts/id1463298887) (Free)

1. Install and open extension
2. Copy and paste below code
3. Open extension settings
4. Save

<details>
<summary>Copy and Paste</summary>

```js
// ==UserScript==
// @name         Hide Elements Containing "Khloé in Wonder Land" on Twitter and X
// @description  Hides elements with class "css-175oi2r r-1adg3ll r-1ny4l3l" on twitter.com and x.com if they contain "Khloé in Wonder Land"
// @author       Noah Maranesi
// @namespace    https://github.com/noahmaranesi
// @match        https://twitter.com/*
// @match        https://x.com/*
// @grant        none
// @version      1.1
// ==/UserScript==

(function() {
    'use strict';

    function hideElementsInSidebar() {
        const sidebarColumn = document.querySelector('[aria-labelledby="accessible-list-0"], .sidebarColumn'); // Update to actual class or selector for sidebar

        if (sidebarColumn) {
            sidebarColumn.querySelectorAll('.css-175oi2r.r-1adg3ll.r-1ny4l3l').forEach(element => {
                if (element.innerText.includes("Khloé in Wonder Land")) {
                    element.style.display = "none";
                }
            });
        }
    }

    hideElementsInSidebar();

    const observer = new MutationObserver(hideElementsInSidebar);
    observer.observe(document.body, { childList: true, subtree: true });
})();
```
</details>
