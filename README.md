# cdn-assets

Public static image assets served globally through [jsDelivr](https://www.jsdelivr.com/). This repository is intentionally project-agnostic: any project may reference any file here by its CDN URL.

All files are served as URL strings, not modules. Render them with `<img src="…">` or CSS `background-image`.

## CDN usage

```text
https://cdn.jsdelivr.net/gh/taozhuowei0114/cdn-assets@<ref>/<folder>/<file>
```

- Branch (development): `https://cdn.jsdelivr.net/gh/taozhuowei0114/cdn-assets@main/images/general/example.webp`
- Version tag (production, recommended): `https://cdn.jsdelivr.net/gh/taozhuowei0114/cdn-assets@v1.0.0/images/general/example.webp`
- Cache bust without a new tag: append `?v=20261124`

`@main` may take minutes to hours to refresh after an update. Use a commit hash or version tag when the URL must be immutable.

## Folder structure

```text
cdn-assets/
├── images/
│   ├── general/       # general-purpose photos and illustrations
│   ├── portraits/     # portrait and beauty photography
│   ├── products/      # product packshots and flatlays
│   └── backgrounds/   # full-page and hero backgrounds
├── branding/          # logos, icons, wordmarks
├── mockups/           # UI and campaign mockup screenshots
└── placeholders/      # staging and wireframe images
```

Add a new subfolder when an existing one does not fit. Keep one canonical location per file.

## File naming

Use lowercase, hyphenated, descriptive names. No spaces, no uppercase, no `img1.png`-style names.

```text
✅ serum-packshot-lilac.webp
✅ portrait-low-bun.webp
❌ IMG_20261124_FINAL_v2.PNG
❌ Screenshot 2026-11-24.png
```

## Compression targets

Compress before upload. jsDelivr limits a single GitHub file to about 20 MB; keep files far below that.

| Format | Use case | Target |
|---|---|---|
| `.webp` | photos, mockups, screenshots | < 150 KB |
| `.jpg` | photos, fallback | < 200 KB |
| `.png` | transparent logos | < 100 KB |
| `.svg` | icons, vector logos | < 30 KB |

Recommended tools: Squoosh, TinyPNG, SVGOMG.

## Updating files

1. Add or replace the file in the correct folder.
2. Commit with a short message describing the asset.
3. Push to `main`. For a stable URL, create a version tag: `git tag v1.1.0 && git push origin v1.1.0`.
4. Never modify a tagged release — cut a new tag instead.

To force-refresh a `@main` URL immediately, use the [jsDelivr purge endpoint](https://purge.jsdelivr.net/).

## Notes

- The repository is public. Do not upload private or sensitive material.
- jsDelivr is free for personal and commercial use with no bandwidth or request limits, subject to its [terms](https://www.jsdelivr.com/terms).
- Keep only assets you have the right to publish.
