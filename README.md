# Kimia docs

Public product documentation. Written for people using Kimia, not building it.

Built with [Mintlify](https://mintlify.com).

## Running locally

```sh
npm i -g mint
mint dev
```

Serves on `http://localhost:3000` and hot reloads as you edit. Use
`mint dev --port 3333` if `trading-client` already holds that port.

Run from this folder. Mintlify looks for `docs.json` in the working directory.

## Checks

```sh
mint broken-links
```

Two things worth knowing before editing:

MDX parses `{...}` as a JavaScript expression. Braces in a heading break the build.
Escape them as `\{asset\}` or wrap the text in backticks.

Every page must appear in the `navigation` block of `docs.json`. A file that exists
but is not listed will not be reachable.

## Layout

```
docs.json                 site config and navigation
index.mdx                 what Kimia is
how-it-works.mdx          funding rates and delta-neutral, in plain language
is-this-for-me.mdx        who this suits and who it does not
getting-started/          what you need, invite code, account, deposit and bridge, first position
using-kimia/              reading a position, closing, costs, referrals, portfolio and leaderboard
safety/                   risks, custody, troubleshooting
glossary.mdx  faq.mdx     reference
legal/                    terms of use, privacy policy (.md)
logo/  favicon.png        brand assets
```

## Assets

`logo/light.png` is the black wordmark, shown in light mode. `logo/dark.png` is the
white one, shown in dark mode. The key names the mode, not the ink colour.

Both are generated from the same artwork so the geometry matches exactly when the
theme toggles. The source exports in `landing/landing/public/` differ by about nine
percent in ink ratio, so do not copy them in directly without normalising.

## Writing style

Plain language, short sentences. Define a term before using it.

No em dashes and no emoji.

Be honest about risk. This documentation covers a product that handles real money on
live exchanges, and `safety/risks.mdx` is a real page rather than a disclaimer.
