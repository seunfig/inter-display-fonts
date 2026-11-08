# Inter Display — web files

Inter Display (version 4.000) as WOFF2, latin subset, for use on the web.

Served from this repository through jsDelivr, which sets
`access-control-allow-origin: *` and a one year immutable cache.

## Files

`variable/InterVariable.woff2` — 103 KB. The variable font: `wght` 100–900 and
`opsz` 14–32, so it sharpens into the Display cut automatically at large sizes.
One file replaces all static weights.

`variable/InterVariable-Italic.woff2` — 113 KB, the matching true italic.
Version 4.001, taken from the Inter 4.1 release that ships with the Align UI
design system, latin subset.

`subsets/latin/InterDisplay-{Light,Regular,Medium,SemiBold,Bold}.woff2` — 28–30 KB each.
Static Display cut, kept for reference; not used by the site.
Subset covers Latin-1 plus general punctuation (em dash, curly quotes, bullet),
the arrow U+2192, the euro sign and the trademark sign. Converted from the
upstream TTFs with `fontTools`, hinting stripped.

## Usage

```
@font-face {
  font-family: 'Inter Display';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url(https://cdn.jsdelivr.net/gh/seunfig/inter-display-fonts@v1.0.0/subsets/latin/InterDisplay-Regular.woff2) format('woff2');
}
```

Weights published: 300, 400, 500, 600, 700.

## Licence

Inter is licensed under the SIL Open Font License 1.1. See `LICENSE.txt`.
The OFL permits redistribution and web embedding, including from a CDN, as
long as the licence travels with the files and the font is not sold on its own.

## Variable font

```
@font-face {
  font-family: 'Inter Variable';
  font-style: normal;
  font-weight: 100 900;
  font-display: swap;
  src: url(https://cdn.jsdelivr.net/gh/seunfig/inter-display-fonts@v1.1.0/variable/InterVariable.woff2) format('woff2');
}
```

`font-optical-sizing: auto` is the CSS default, so `opsz` follows `font-size`
with no extra declarations: 12px body text gets the text cut, 48px headings get
the Display cut.

The static Display builds and the variable font use different family names
(`Inter Display` vs `Inter Variable`), so they can coexist. Don't register both
against the same name: two `@font-face` blocks claiming one family with
overlapping `wght` ranges let the later one win, and the static file has `opsz`
baked at 32, which would silently disable optical sizing.

## Version history

- `v1.0.0` — static Inter Display, weights 300–700, from Inter 4.000.
- `v1.1.0` — Inter Variable 4.000.
- `v1.2.0` — Inter Variable 4.001 (Inter 4.1 release) plus the variable italic.

## Inter Display, static (v2.0.0)

`display/InterDisplay-{Regular,Medium,SemiBold,Bold}.woff2` — 29–30 KB each,
Inter 4.001 from the Inter 4.1 release, latin subset.

```
@font-face { font-family:'Inter Display'; font-weight:400; src:url(…@v2.0.0/display/InterDisplay-Regular.woff2) }
@font-face { font-family:'Inter Display'; font-weight:500; src:url(…@v2.0.0/display/InterDisplay-Medium.woff2) }
@font-face { font-family:'Inter Display'; font-weight:600; src:url(…@v2.0.0/display/InterDisplay-SemiBold.woff2) }
@font-face { font-family:'Inter Display'; font-weight:700; src:url(…@v2.0.0/display/InterDisplay-Bold.woff2) }
```

The Medium and SemiBold files declare `Inter Display Medium` and `Inter Display
SemiBold` in their name tables (legacy style naming). The `font-family`
descriptor in `@font-face` overrides that, so all four render as one family with
four weights. Don't rely on the name table.
