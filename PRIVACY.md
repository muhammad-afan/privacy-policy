# Snipframe privacy policy

**Snipframe collects nothing, sends nothing, and stores nothing outside your own
browser.**

## Data collection

None. There is no analytics, no telemetry, no crash reporting, no usage
statistics, no account, no login, and no server.

## Network access

Snipframe makes **no network requests of any kind**. There is no `fetch`, no
`XMLHttpRequest`, no WebSocket and no `sendBeacon` anywhere in the shipped code.

You can verify this yourself: open DevTools on the extension's service worker and
the page you are capturing, and watch the Network tab through a full capture. It
stays empty. You can also inspect the source — this is a small codebase and the
absence is greppable.

## What is stored, and where

Everything below lives on your device only.

| What | Where | Why |
|---|---|---|
| Your settings | `chrome.storage.sync` | So they follow you across Chrome profiles you are signed into. Synced by Chrome, to your own Google account, never to us. |
| The last 10 captures | IndexedDB, in this browser | The history list in the options page. Clearable at any time with the "Clear history" button, which deletes them immediately. |
| Capture session state | `chrome.storage.session` | Cleared when the browser closes. Used to detect and clean up after an interrupted capture. |

Turning off "Keep a local history" stops captures being stored at all.

## Page access

Snipframe requests **no site access at install time**. Its `host_permissions`
list is empty.

Chrome grants it a transient, single-tab permission (`activeTab`) only at the
moment you click the toolbar icon or press the keyboard shortcut. That grant is
what allows it to take the screenshot, and it lapses on navigation. Outside that
window, Snipframe cannot read any page.

One advanced setting, "Keep the picker ready on every site", asks for broader
access. It ships disabled, it is only ever requested in response to you turning it
on, and turning it off revokes it.

## Your images

Your screenshots are created, styled and stored entirely on your device. They go
to your clipboard or your downloads folder because you asked for them to. They are
never uploaded anywhere, because there is nowhere to upload them to.

## Contact

Snipframe has no backend, so there is nothing to request deletion of. Issues and
questions belong on the project's issue tracker.
