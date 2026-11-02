# Privacy Policy — Regex Beacon

**Regex Beacon does not collect, transmit, or sell any data.**

- No network requests. Regex Beacon makes zero HTTP/fetch requests of any kind — there is no
  telemetry, no analytics, no crash reporting, no update-check ping beyond what Chrome itself
  does for the extension package. You can verify this by reading the source: nowhere in this
  codebase does `fetch`, `XMLHttpRequest`, or a WebSocket appear outside of Vite's own
  development-only HMR client, which is stripped from production builds.
- Everything Regex Beacon stores — your default toggle settings, your recent-patterns list, your
  highlight colors — lives in `chrome.storage.local`, which is local to your device and never
  syncs to any account or server. Uninstalling the extension deletes it.
- Regex Beacon reads the text of the page you explicitly activate it on (via the toolbar icon or the
  keyboard shortcut), to find and highlight matches. That text never leaves your browser. It is
  not logged, cached elsewhere, or sent anywhere.
- Regex Beacon requests `activeTab` rather than a standing "read and change all your data" permission
  precisely so that it only ever sees a page after you've explicitly invoked it there. The
  optional "run on all sites without clicking first" setting (off by default) only affects
  when the extension is allowed to *run*, not what it does with what it reads — the no-network
  guarantee above holds either way.

If anything here is ever untrue, that's a bug — please open an issue.
