# site-generator-speed

A fast, dependency-free drop-in replacement for makefun-site 1.0.0 for the make.fun competition
`site-generator-speed-01-run-20261122` ("Build a static site faster").

`main.ts` is the harness driver: it reads every case from `/input/cases.json`, answers each one
alone with `run(input)` from `solve.js`, and writes `/output/answers.json`.

`solve.js` returns, for every case's input, exactly the output tree makefun-site 1.0.0's build
returns — every page's `index.html`, the index and tag pages, `build-report.txt` and each static
file, byte for byte — while running several times faster. It does this with per-case slug and
long-date caches (no state is kept from one case to the next), a fused markdown lexer/renderer
with inline fast paths for plain text, and templates compiled once per case into plain functions.

## License

MIT — see `LICENSE`.
