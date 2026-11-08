# Ruach

**God-breathed. Every word.**

Ruach (ROO-akh) is a free Bible app you scroll like a social feed, with in-depth study one tap away. It runs on donations, not subscriptions.

> All scripture is given by inspiration of God, and is profitable for doctrine, for reproof, for correction, for instruction in righteousness: That the man of God may be perfect, throughly furnished unto all good works.
> — 2 Timothy 3:16–17 (KJV), the project's mission

## What's in it

- **Scroll feed**: full-screen verses over painted scenes, with Amen, Save, Listen, and Share. It mixes in guided studies, breath prayers, quick quizzes, and "did you know" cards.
- **Read Through mode**: the whole Bible verse by verse, Genesis to Revelation, picking up where you left off.
- **Read tab**: any book and chapter, plus search across all 31,000+ verses.
- **47 translations**: 15 in English, 26 other languages, and the original Hebrew Old Testament and Greek New Testament.
- **Go deeper on any verse**: the verses around it, book facts (author, date, key verse), side-by-side translations, the Hebrew or Greek word by word with dictionary entries, up to 10 cross references, and a journal prompt.
- **Guided studies**: 26 hand-written studies with plain-language meaning, setting, a word study, and a prayer.
- **Grow tab**: team devotionals and eight themed journeys.
- **My Walk**: streaks, a daily goal, Read Through progress, saved verses, and a private journal.

## Run it locally

The app is static files. Serve the `web` folder with any web server:

```bash
cd web
python3 -m http.server 8000
```

Then open http://localhost:8000. Opening `index.html` directly from the file system won't work, because the browser blocks it from loading the Bible files.

## Publish it free with GitHub Pages

1. In this repo, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions**.
3. Push to `main`. The workflow in `.github/workflows/pages.yml` publishes the `web` folder.

## Project layout

| Path | What it holds |
| --- | --- |
| `web/index.html` | The whole app: layout, styles, and code in one file |
| `web/bibles/` | One file per translation (gzip-compressed JSON, base64 text) and `meta.json`, the translation list |
| `web/orig/` | Hebrew and Greek words per book (`0`–`65`), plus the Hebrew (`lexH`) and Greek (`lexG`) dictionaries |
| `web/xref/` | Cross references per book |
| `web/devotionals.json` | Published devotionals |

Each data file is gzip-compressed JSON stored as base64 text. The app decodes it in the browser and caches it on the device.

## Devotionals

In the Claude-hosted version, the owner posts devotionals in the app, and they're stored in that page's database. On other hosts, such as GitHub Pages, the app reads `web/devotionals.json` only. To publish devotionals there, add them to that file in this shape:

```json
{"items":[{"id":"d1","title":"New every morning","ref":"Lamentations 3:22-23","body":"First paragraph.\n\nSecond paragraph.","prayer":"Lord, ...","by":"Tim","date":"2026-11-08"}]}
```

The store apps will move devotionals to a proper backend. See the roadmap.

## Donations

Ruach is free and supported by donations. The Support button stays a placeholder until donations have a proper nonprofit home: a church fund, a fiscal sponsor, or Ruach's own 501(c)(3). To connect it, set `DONATE_URL` in `web/index.html`.

## Roadmap

1. A legal home for donations (church, fiscal sponsor, or 501(c)(3)).
2. A website with a privacy policy, terms, support, and donation pages.
3. iPhone and Android apps built with Capacitor, with offline Bibles and daily verse notifications.
4. Apple and Google developer accounts, TestFlight, and Google's 14-day closed test.
5. Store launch, then licensed translations (ESV, NIV, NLT) through the Digital Bible Library.

## Credits and licenses

The app code is under the MIT License (see `LICENSE`). The Bible texts and study data have their own terms; see [DATA_LICENSES.md](DATA_LICENSES.md).
