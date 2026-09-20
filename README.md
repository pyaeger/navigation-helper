# Navigation Trainer

A single-page, offline-capable practice tool for learning to travel independently by rideshare, designed for mobile phones.

- **Live app:** https://pyaeger.github.io/navigation-helper/
- Fully self-contained: one HTML file, no accounts, no analytics, no external requests.
- Works offline. Nothing is transmitted; nothing is stored off-device.
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

## Files

- `index.html` — the entire app (markup, styles, logic)
