# Inter Display — web files

Inter Display (version 4.000) as WOFF2, latin subset, for use on the web.

Served from this repository through jsDelivr, which sets
`access-control-allow-origin: *` and a one year immutable cache.

## Files

`subsets/latin/InterDisplay-{Light,Regular,Medium,SemiBold,Bold}.woff2` — 28–30 KB each.
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
