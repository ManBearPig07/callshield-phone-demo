# Public Demo Hosting Guide

## What to host

Host only the `public_demo/` folder. The file Seth should open is:

```text
public_demo/index.html
```

Do not publish the private repository, `.git` folder, configs, local SQLite database files, tests, or server code. The public demo is self-contained static HTML and does not need Python, Twilio, Stripe, paid speech tools, or live phone service.

The page includes an inline CSP meta tag that blocks external connections and external assets while allowing the inline CSS and JavaScript required for a one-file static demo.

## Safe hosting options

Use any static file host that gives Gary a public HTTPS link:

- Netlify drag-and-drop site.
- Vercel static project.
- A separate public GitHub Pages repository containing only `public_demo/`.
- S3, Cloudflare Pages, or another static host.

The important rule is to upload only this folder, not the private repo.

## What link to text Seth

The hosted phone-demo link is:

```text
https://manbearpig07.github.io/callshield-phone-demo/
```

This link is served from a separate public GitHub Pages repository containing only the static demo files. The private product repo remains private.

## How Seth runs it on his phone

1. Open the public hosted link.
2. Tap **Start**.
3. Tap **Run phone demo seed**.
4. Tap **Walkthrough** for the click-by-click tutorial.
5. Tap **Live Demo**.
6. Try **Home inspection**, **HVAC**, **Safety**, **Wrong service**, **Out of area**, and **Vendor**.
7. Tap **Ledger** and **ROI**.
8. Tap **Copy text to Seth** or **Share this demo** on **Next** if he wants to forward the demo.
9. Review **Integrations**, **Setup**, and **Next**.

## What the demo does

- Explains CallShield from scratch.
- Includes a click-by-click Walkthrough tab for a nontechnical user.
- Shows why CallShield is not a generic AI receptionist.
- Runs transcript-derived static demo scenarios on the phone.
- Builds a local in-browser Lead Waste Ledger.
- Shows a human-readable verdict card before technical JSON.
- Shows recovered revenue, recovered gross profit, ROI multiple, and payback.
- Exports a CSV from the phone browser and includes View CSV / Copy CSV fallbacks.
- Shows optional open-source integrations as JSON.
- Generates valid setup JSON for a customer pilot.

## What the demo does not do

- It does not place or receive live calls.
- It does not require Twilio, Stripe, paid STT, paid TTS, or paid LLMs.
- It does not collect raw card data by voice.
- It escalates safety, regulated, angry-caller, human-request, and low-confidence language to a human.
- It does not give legal advice, medical triage, or rehab counseling.
- It does not implement outbound cold calling or lead resale.
- It does not expose the private repo or any secrets.

## PWA decision

No PWA files are included in this pass. That is intentional: the goal is a one-link, always-current static demo for Seth. A service worker could cache an older version on a phone and make last-minute demo updates harder to verify. Add PWA support later only after the hosted demo URL and update process are stable.
