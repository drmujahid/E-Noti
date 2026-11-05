# To E-Noti, or to Manual?

Offline-first, mobile-responsive web app prototype for healthcare workers in Malaysia.

## How to use

- **Immediate use:** Open `index.html` in a modern browser. Search and filter work without an internet connection.
- **Share as a website:** Upload `index.html`, `manifest.webmanifest`, `service-worker.js`, and `icon.svg` to any static HTTPS host (e.g., GitHub Pages, Netlify, Cloudflare Pages).
- **Add to home screen:** Once hosted over HTTPS, open in Safari on iOS → Share → Add to Home Screen, or use the browser's install option on supported Android browsers.
- No accounts, backend, external JavaScript or patient data collection.

## Dataset

- 48 named diagnoses from Borang Notifikasi Penyakit Berjangkit (Rev/2023), P.U. (A) 253 / 2023, Section B entries 1–48.
- Entry #49 (any other life-threatening microbial infection) is kept as a separate **Semak PKD** card, rather than declared exempt from notification.
- Local surveillance list supplied by the user: 10 administrative notifications, 3 event-based, 4 lab-based. Brucellosis appears in two source categories. The app shows 17 distinct topics by splitting Q fever and Brucellosis for search.
- `urgent24` list is from the bold yellow statement in the Rev/2023 form. Both dengue and DHF are treated as dengue for this flag.

## Very important limitations

- **Not an official KKM application.** Review with the respective PKD/JKN before clinical rollout.
- Different districts may use e-Notifikasi for Brucellosis, Chikungunya and some other conditions listed under the local surveillance dataset. These carry warnings in the app.
- Separate case definitions, specimen requirements and latest notification policies are **not** determined by this app.
- e-Noti does not replace the separate **telephone notification within 24 hours** required for listed diseases.
- A manual form may also be used as a fallback for a statutory e-Notifiable disease when the system is down. The word “Manual” in this app specifically means the **user-supplied surveillance pathways**, not this fallback.

## Key references

1. P.U.(A) 253 / 2023, official Rev/2023 notice form: https://jknjohor.moh.gov.my/hsajb/index.php/warga-hsa1/muat-turun-borang/category/79-borang-notifikasi?download=600%3Anotifikasi-penyakit-berjangkit-rev-2010-bm
2. Example of PKD-specific eNotifikasi variation: https://sites.google.com/moh.gov.my/cdcpkdklgt

## Updating the disease list

All content is stored as plain JavaScript constants `diseases`, `manual`, `urgent24` and `special` near the bottom of `index.html`. Edit these arrays, then increment the cache name in `service-worker.js` when publishing a new release.
