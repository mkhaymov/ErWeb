# Sample artist data package

This folder demonstrates the data files an artist can host for the shared ErWeb viewer. It uses artwork images already included in the repository so the example can be tested without adding duplicate image files. The sample brand is explicitly marked as sample data.

## Try it locally

Serve the repository root over HTTP, then open:

```text
http://localhost:8000/index.html?config=examples/sample-artist/config.json
```

For example, from the repository root:

```bash
python -m http.server 8000
```

The sample config points back to the shared viewer pages and points to this folder's `galleries.json` and `images.json`. The relative artwork and logo paths resolve to existing repository assets.

## Use the sample as a template

Copy this folder to a location you control, update `config.json` with your own brand and data URLs, and update the gallery and artwork JSON with your content. Replace the sample image paths with URLs to images you host. For a separate domain, configure CORS to permit the viewer to fetch your config and JSON files.

See the repository README for the full data schema and hosting guidance.
