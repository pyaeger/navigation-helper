# Navigation Trainer

A single-page, offline-capable practice tool for learning to travel independently by rideshare, designed for mobile phones.

- **Live app:** https://pyaeger.github.io/navigation-helper/
- One HTML file. No accounts, no analytics, and no third-party requests on page load.
- **Not currently offline-capable.** There is no service worker, so the page needs a connection to load. Once it has loaded it makes no further requests. See *Known limitations*.
- Install on iPhone: open the link in Safari → Share → **Add to Home Screen**.

## What it does

Walks through a ride step by step, one card at a time, with a **Start / Next** flow and an **I Did This** confirmation so the user can keep their place without re-reading the whole page.

A **Bigger Text** toggle raises the body size for readability, and a **Practice Route** lets someone rehearse the sequence before they need it for real.

## If Something Goes Wrong

The part that matters most. Four labelled recovery paths, reachable at any point:

- Driver going wrong way
- Wrong pickup
- Wrong destination
- Feel unsafe

Each is written to be readable under stress: short sentences, concrete next action, no jargon.

## Design notes

Built for someone who needed it, not as a demo. The constraints followed from that: it has to work with no signal, on an older phone, without an account, and without anyone having to trust a third party with where they are going.

## Known limitations

Verified by reading the source, September 2026.

| Claim | Status | Confidence |
|---|---|---|
| No third-party requests on page load | True — no external `script`, `link`, `img` or `fetch`. The only external URL is the *Open Google Maps* button, which the user chooses to tap. | H |
| Works offline | **False today.** No `sw.js` and no service-worker registration. Add to Home Screen gives a full-screen launch, but without a cached service worker iOS shows "No internet connection" when offline. | H |
| Progress is remembered | **False.** The app uses no `localStorage`; *I Did This* state is lost on reload. | H |

**The offline gap matters here more than in a normal app.** This tool exists partly for the moment someone feels unsafe or is being taken the wrong way — which is also a moment they may have no signal. Adding a service worker would close that gap and is the single highest-value change to this project.

## Files

- `index.html` — the entire app (markup, styles, logic)
