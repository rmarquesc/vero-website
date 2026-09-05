# Vero — website

The public site for **Vero**, a verifiable credibility layer for people and
organisations publishing online, built on [Midnight](https://midnight.network)
for the [Midnight Buildathon](https://akindo.io).

The contract and its toolchain live in a separate repository:
[rmarquesc/vero-demo](https://github.com/rmarquesc/vero-demo).

## Pages

| File | What it is |
|---|---|
| `index.html` | Landing page — problem, mechanism, scope, source types, competitive landscape, personas, Web3 use case, roadmap, status |
| `progress.html` | Live status and a chronological build log, updated as work lands |
| `slides.html` | Seven-slide pitch deck, with arrow-key and `#s1`–`#s7` navigation |
| `COPY.md` | The full copy for all three pages in one place, for editing without touching markup |
| `assets/styles.css` | Shared stylesheet for all three pages |

Plain HTML and CSS. No build step, no dependencies, no JavaScript beyond the
deck's slide navigation.

## Running it locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` directly from the filesystem also works.

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which publishes to
GitHub Pages. The repository's **Settings → Pages → Source** is set to
**GitHub Actions**.

The workflow's path filter covers `index.html`, `progress.html`, `slides.html`,
`assets/**` and the workflow itself — a change confined to `COPY.md` or this
README will not trigger a deploy, which is intentional.

## Editing the build log

`progress.html` has a commented-out entry template at the top of the log
section. Copy it, fill it in, and paste it above the newest entry — the log
reads newest first. Status classes are `done`, `in-progress` and `blocked`.

Two things to remember: bump the `last updated` date in the stamp row, and keep
`COPY.md` in step so the two do not drift apart.

## License

Apache License 2.0.
