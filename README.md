# Device end-of-support dataset

Published security and OS update end dates for **105 consumer devices** — phones, tablets and laptops, plus watches, earbuds, consoles and smart home devices — with source citations for every entry.

Most "how long will this last" advice is guesswork. This is the underlying data: when each manufacturer says it stops shipping patches, and where that claim comes from.

Free to use with attribution. If it saves you a week of reading vendor support pages, that is the point.

## What is in it

`devices.json` — one record per device:

```json
{
  "id": "pixel-6",
  "name": "Pixel 6",
  "brand": "Google",
  "type": "phone",
  "released": "2021-10",
  "osUpdateEnd": "2026-10",
  "securityEnd": "2026-10",
  "supportConfidence": "official",
  "sources": [
    { "label": "Google Pixel update schedule", "url": "https://support.google.com/pixelphone/answer/4457705" }
  ],
  "lastVerified": "2026-09-28"
}
```

`supportConfidence` tells you how much to trust the date:

| Value | Meaning | Count |
| :--- | :--- | ---: |
| `official` | The manufacturer publishes this exact end date | 21 |
| `announced-policy` | Derived from a stated policy, e.g. "7 years from launch" | 34 |
| `pattern-estimate` | Inferred from the vendor's track record. Treat as a planning estimate | 50 |

Nearly half the dataset is estimated rather than published. That is a fact about manufacturer transparency, not a shortcut taken here, and it is labelled so you can filter on it.

## Coverage

105 devices: Apple 31, Samsung 26, Google 11, Lenovo 6, Amazon 4, OnePlus 3, and others.

By type: 52 phone, 30 laptop, 15 tablet, 2 watch, 2 earbuds, 2 console, 2 smarthome.

Watches, earbuds, consoles and smart home devices don't get versioned OS upgrades the way phones do, so their `osUpdateEnd` is `null` unless the maker states one. The same goes for `wearTier` and `wearFactors`, which the site's wear model only defines for phones, tablets and laptops so far.

## Already past their security cutoff

Pixel 3, Galaxy S9, LG V60 ThinQ, Pixel 5, Galaxy S20, Galaxy Note 20, Lenovo Tab P11 (2nd gen), Galaxy Tab A8, Galaxy S21, Nest Hub (2nd Gen), Moto G Power, Fire HD 10 (11th gen), Galaxy Buds 2 Pro

## Losing support within 12 months

| Device | Last patch |
| :--- | :--- |
| Pixel 6 | 2026-10 |
| Pixel Watch 2 | 2026-10 |
| Galaxy S22 | 2027-02 |
| Galaxy Tab S8 | 2027-02 |
| Galaxy A14 | 2027-05 |
| Fire 7 (12th gen) | 2027-06 |
| Fire HD 8 (12th gen) | 2027-06 |
| Motorola Razr+ | 2027-06 |
| Nothing Phone (2) | 2027-07 |
| OnePlus Nord 3 | 2027-07 |
| Pixel 6a | 2027-07 |
| AirPods Pro (2nd Gen) | 2027-09 |
| MacBook Air (Intel, 2020) | 2027-09 |
| MacBook Pro 13" (Intel, 2019) | 2027-09 |
| iPhone XR | 2027-09 |

## Why this matters

A device's usable life ends at whichever comes first: the hardware wearing out, or the vendor stopping patches. For most devices built since 2020 it is the second, and that is a policy decision rather than a physical limit.

A battery is a $40 part. There is no part you can order that fixes an unpatched kernel.

## Corrections

Open an issue. Manufacturers change these policies quietly — Google extended the Pixel 6, 7 and Fold from three years of OS updates to five in December 2024, and plenty of sources still carry the old dates. A correction with a source link is genuinely welcome.

## Licence

[CC BY 4.0](LICENSE). Use it commercially, modify it, redistribute it. Credit [devicelifespan.com](https://devicelifespan.com).

## Related

[devicelifespan.com](https://devicelifespan.com) puts this data behind a calculator that compares it against realistic battery wear for your usage, so you get a date rather than a table.
