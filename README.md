# craigslist-hunter

Scrapes Craigslist SF for apartment listings and emails you a digest. Runs on a schedule via Browserbase.

## What it does

Searches sfbay.craigslist.org with your filters, narrows results to a radius around a zip code using actual listing coordinates, and sends a formatted email with the results via Resend.

## Setup

You'll need:
- A [Browserbase](https://browserbase.com) account
- A [Resend](https://resend.com) account

Set these environment variables:
```
BROWSERBASE_API_KEY=
BROWSERBASE_PROJECT_ID=
RESEND_API_KEY=
RECIPIENT_EMAIL=
```

## Params

| param | type | default | description |
|---|---|---|---|
| `zipcode` | string | `"94117"` | center of search (SF zips only) |
| `radius` | number | `1.5` | miles from zip code |
| `minBeds` | number | `2` | minimum bedrooms |
| `maxPrice` | number | `6000` | max monthly rent |
| `parking` | boolean | `false` | require off-street parking |
| `recipient` | string | `RECIPIENT_EMAIL` env | override the email recipient |

## Running

```bash
pnpm install
```

Deploy and invoke via the Browserbase SDK functions CLI, or trigger it on a schedule from the Browserbase dashboard.
