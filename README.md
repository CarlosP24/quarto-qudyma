# QUDYMA reveal.js theme for Quarto

The slide theme of the QUDYMA group (ICMM-CSIC) for [Quarto](https://quarto.org) talks:
a 1600 × 900 canvas, Montserrat, the CSIC red accent and a muted physics palette, part
dividers with kickers, assertion titles, and KaTeX bundled so that a deck works offline and
as a single HTML file.

## Install

A new talk, with the starter deck:

```bash
quarto use template CarlosP24/quarto-qudyma
```

An existing talk folder:

```bash
quarto add CarlosP24/quarto-qudyma
```

Then, in the YAML header:

```yaml
format: qudyma-revealjs
```

## Build

```bash
quarto preview talk.qmd                                            # live preview
quarto render talk.qmd -M embed-resources:true -o talk-standalone.html   # one file, offline
quarto render talk.qmd                                             # talk.html + talk_files/
```

Render the standalone file first: the plain render's `talk_files/` is removed by it.
Present `talk-standalone.html` in Chrome or Firefox: `F` full screen, `S` speaker view,
`M` menu, `Esc` overview, `B` black screen. PDF backup: open `talk.html?print-pdf` in
Chrome and print (landscape, no margins, background graphics).

## What the theme provides

**Title slide** (YAML): `title`, `author` (only the speaker), `affiliation`, `event`,
`venue`, `date`, `paper`, `paper-url`, `hero` (list of `{src, caption, class}`; `class:
full` fills the panel, `wide` spans it), `logos` (paths or `{src, height}`), `title-note`,
`footer`. `logo` goes to the top-right corner of every content slide (hide with
`.no-logo`).

**Parts**: `# Title {.part data-num="01" data-kicker="01 · Short name" data-sub="..."}`,
optionally with `![](art.svg){.part-art}`. Every following slide shows the kicker above its
title (override with `data-kicker`, hide with `.no-kicker`).

**Slides**: titles are assertions. `.no-rule`, `.no-chrome` (no footer or number).

**Blocks**: `.key` take-away (`.green`, `.navy`, `.orange`, `.plain`), `.lead`, `.eq`,
`.refs` (bottom, centred, grey; your own name in bold), `.figcap`, `.card`, `.stack`
(overlaid layers of one figure), `.avatars` / `.avatar`, `.photo-map` with `.map-box` and
`.map-pin`, `.conc`.

**Talk structure**: `.hook` (opening statement and question), `.ccards` / `.ccard`
(conclusion cards, 2–4), `.thanks` (who I am, people, `.qr` paper panel, `.funding` logo
strip). `template.qmd` shows each of them.

**Inline**: `[class D]{.chip .red}` (also `.green`, `.navy`, `.ink`, `.red-soft`, …),
`.muted`, `.small`, `.smaller`, `.tiny`, `.red`, `.green`, `.navy`, `.hl-red`, `.hl-green`,
`.nowrap`, `.semibold`.

**Fragments**: reveal's own, plus `.fade-up` and `.dim-out`.

**Math**: `$...$` and `$$...$$` as usual. The theme sets `html-math-method: gladtex` and
renders the TeX with the KaTeX bundled in its plugin, so math works offline and in
standalone files; for KaTeX in your own scripts, `window.katex` is there too.

**Colours**: every palette colour is a CSS custom property (`--qd-red`, `--qd-ink`,
`--qd-navy`, `--qd-green`, `--qd-orange`, their `-tint`s, …) for figures and scripts.

## Contents

| Path | What |
|---|---|
| `_extensions/qudyma/` | The extension: `qudyma.scss`, `title-slide.html`, the reveal plugin (kickers, chrome, logo, math with the bundled KaTeX), Montserrat |
| `template.qmd`, `assets/` | Starter deck with placeholder art, photos and logos |

Montserrat is under the SIL Open Font License (`fonts/OFL.txt`), KaTeX under the MIT
license (`plugin/katex/LICENSE`); the rest is MIT (`LICENSE`).
