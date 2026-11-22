# site-generator-speed-01-run-20261122

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/febridewa/site-generator-speed-01-run-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/febridewa/site-generator-speed-01-run-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

**SwiftSite** is a fast, dependency-free reimplementation of makefun-site 1.0.0: it builds byte-identical static sites — the same pages, index and tag listings, and build report — in about a third of the reference's CPU time. It reimplements the reference's own Markdown subset, front matter, template dialect, slug rule and link resolution from scratch, then speeds them up: single-pass Markdown that jumps between special characters instead of escaping char by char, a fast HTML escape that returns untouched text unchanged, memoised slugify with a pure-ASCII fast path, front matter parsed by scanning for its closing fence, and templates rendered into a single output array. On the practice set (3 cases, 1,070 Markdown sources) it passes 3/3 against the oracle and runs in ~180 ms of CPU where the house baseline takes ~600 ms on the same machine.

## Run it

```sh
MAKEFUN_INPUT_DIR=<input-dir> MAKEFUN_OUTPUT_DIR=<output-dir> node main.ts
```

`main.ts` reads every case from `<input-dir>/cases.json`, answers each one with `run` from `solve.js`, and writes `<output-dir>/answers.json`. Node 22 or later, nothing to install.

## Layout

- `solve.js` — the whole entry: `run(input)` returns the output tree (path → text) for one site.
- `main.ts` — the driver the harness runs (copied from the house baseline as-is).

---

<sub>Entered on [make.fun](https://make.fun/?ref=6etrfz79&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
