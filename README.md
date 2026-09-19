# workshop — the published landing page

This repository is a **publishing destination only**. It holds no page source.

The landing page at https://amitdobry.github.io/workshop/ is built from the
[`amitdobry/memory-game`](https://github.com/amitdobry/memory-game) repository:
`public/index.html` and the three modules it imports (`public/js/attribution.js`,
`public/js/api.js`, `public/js/acquisition.js`). **Edit the page there.** Nothing in
this repository is edited by hand.

The workflow in `.github/workflows/publish.yml` checks out `memory-game`, assembles
those files and deploys them to this repository's GitHub Pages. It runs:

- on `repository_dispatch` (event `memory-game-updated`), which memory-game's own
  Pages workflow sends when a publishing token is configured there — publish within
  a minute of a push;
- every 15 minutes on a schedule, skipping the deploy when the live site already
  serves the current memory-game commit — the fallback when no token is configured;
- on demand, from the Actions tab ("Run workflow").

The file `SOURCE_COMMIT` on the live site names the memory-game commit it was built from.
