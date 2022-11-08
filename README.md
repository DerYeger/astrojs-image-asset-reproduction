# `@astrojs/image` reproduction

Reproduction for https://github.com/withastro/astro/issues/5171.

## Guide

1. Install dependencies using pnpm: `pnpm install`

2. Build both projects: `pnpm build`

## Results

The results of the `Asset.glob` will be printed to the console.

### Latest

`[ '/assets/full-logo-light.0279a7f5.png' ]`

### Old

`[ '/assets/full-logo-light.png' ]`

## Problem

Both versions have paths *ending* in `/assets/full-logo-light.png` (i.e., no hash as well) for `astro dev`.

Since the latest version has a hashed `src`, images can't be filtered by their known name at build time.
This was not the case in v0.3.7.
