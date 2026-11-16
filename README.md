# Chronos browser preview

Static deployment of the historical spacetime prototype. This branch is deployment output only; do not merge it into `main`.

Target GitHub Pages URL: https://ar5336.github.io/History/

## Source and data

The editable prototype source and local runnable copy are packaged in the [temporary demo ZIP in draft PR #1](https://github.com/ar5336/History/pull/1).

Historical polygons come from [Historical Basemaps by Andre Ourednik and contributors](https://github.com/aourednik/historical-basemaps), pinned to `4b5039e50d8d2464b065bd76ad6086cd4597108d`. Exact source files, checksums and transformations are in [`data/manifest.json`](data/manifest.json); the upstream data license is included in [`data/LICENSE.historical-basemaps.txt`](data/LICENSE.historical-basemaps.txt).

The 44 source maps span 500 BCE through 2010 CE. Maps are held unchanged between snapshots, not interpolated into invented border changes. Display categories are inferred conservatively from source labels; the source itself has no state/non-state classification field. The app's **Data & method** panel explains the limitations.

## Refreshing the deployment

From the editable prototype, install dependencies and build with the repository-specific base path:

```sh
npm ci
npm run build -- --base=/History/ --outDir=dist-pages
```

Publish the contents of `dist-pages/` at the root of this `gh-pages` branch, retaining `.nojekyll` and the data attribution. In repository settings, GitHub Pages should deploy from `gh-pages`, root `/`.

There is no backend, package installation, or API key at runtime. Both data files and application code are served by GitHub Pages.
