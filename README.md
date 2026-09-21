# Tag Organizer

A mobile web app to read, label, store, and write NDEF data for NFC tags you own.

## What it does
- **Scan** an NFC tag and see its UID and NDEF records (text, URL, MIME, raw).
- **Save** a scanned tag under a label. Stored locally in your browser.
- **Write** a text or URL record to a writable tag.

## What it does not do
It reads and writes NDEF data only. It cannot emulate a card, copy an
access/parking card, or clone encrypted cards. Browsers have no card-emulation
mode, so a web app cannot present itself to a gate reader as a card.

## Requirements
Web NFC works only in **Chrome on Android**, over **HTTPS** (or localhost).
Desktop browsers and iOS Safari do not support it.

## Run it
Web NFC requires a secure origin. Two easy options:

**A. Free HTTPS host** — put `index.html` on GitHub Pages, Netlify, or Vercel,
then open the URL on your Android phone in Chrome.

**B. Local server + HTTPS tunnel:**
```
cd ~/emulator
python3 -m http.server 8000
# in another terminal, expose it over HTTPS:
npx localtunnel --port 8000
# open the https URL it prints, on your phone in Chrome
```

On first scan Chrome asks for NFC permission. Hold the tag near the top of the
phone.
