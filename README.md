# goGreen

goGreen is a small Node.js script that backdates commits to fill in your GitHub contribution graph — it rewrites `data.json` with a past date and commits it with `git --date`, so the contribution calendar turns green for those days.

## Features

- **Backdated commits** — commits are created with arbitrary past dates via the `--date` git flag.
- **Random pattern** — generates 100 commits on random past dates across the last year, so the contribution graph fills in organically.
- **Simple setup** — one script, four dependencies, no configuration files to manage.

## Tech Stack

- **Runtime:** Node.js (ES modules)
- **Dependencies:** `simple-git` (git operations), `moment` (date math), `random` (date selection), `jsonfile` (data file writes)

## Quick Start

```bash
cd goGreen-main
npm install
node index.js
```

The script will create 100 commits with backdated timestamps and push them to the current branch's remote.

### Project structure

```
goGreen-main/
├── index.js        # main script: markCommit / makeCommits
├── data.json       # scratch file whose date field is rewritten each commit
├── package.json
└── package-lock.json
```

## How it works

1. `makeCommits(100)` picks a random week (`x`, 0–54) and weekday (`y`, 0–6) within the last year.
2. It writes that date into `data.json`, stages the file, and commits it with `--date <that date>`.
3. Repeats recursively until all 100 commits are made, then pushes.

> Note: GitHub's contribution graph counts commits by their **author date** on the default branch — backdated commits appear on their backdated days. Use this on your own repositories.

## License

See [LICENSE](./goGreen-main/LICENSE).

---

Built by Girish Lade — https://ladestack.in
