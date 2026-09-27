# goGreen

goGreen — Node.js script to backdate commits and turn your GitHub contribution graph green.

> App source in `goGreen-main/` (`index.js`, `data.json`).

## How it works
Generates commits for arbitrary past/future dates via `simple-git`, `moment`, `random`, `jsonfile`.

## Getting Started
```bash
cd goGreen-main
npm install
node index.js
```

Configure dates/patterns in `data.json` / `index.js` before running.

## Tech
- Node.js (ESM), simple-git

## Disclaimer
For personal / artistic use. Avoid misrepresenting work history.

## License
ISC — see `LICENSE`.
