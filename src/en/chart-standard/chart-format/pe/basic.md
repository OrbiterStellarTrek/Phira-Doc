# Basic Info

This page describes basic chart data. Note that PEC does not store metadata (title, charter, etc.); that must come from elsewhere. PEC allows at most `30` judge lines; PhiEditor does not allow more. PhiEditor does not support separate X/Y.

## Coordinate system

Screen center is `0,0`. Bottom-left X is `-1024`, Y is `-700`. Top-right X is `1024`, Y is `700`.

## Chart offset

The first line of PEC is the chart `offset` in milliseconds (integer).

## BPM list

Lines starting with `bp` are BPM entries, e.g.:

```txt
bp 0.000 180.000
```

Meaning at beat `0.000`, BPM is `180.000`.
