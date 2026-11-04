# Sample artist data package

This package demonstrates the viewer's configuration and data format with a neutral, generic portfolio presentation. Its sample artworks are JPEG files included in this folder under `images/`; the viewer does not request artwork images from third-party websites.

## Try it locally

Serve the repository root over HTTP, then open:

```text
http://localhost:8000/index.html?config=examples/sample-artist/config.json
```

For example, from the repository root:

```bash
python -m http.server 8000
```

## Use the sample as a template

Copy this folder to a location you control, update `config.json` with your own brand and data URLs, and replace the example gallery and artwork entries with your own content and image URLs. Confirm that you have permission to publish any images you add. For a separate domain, configure CORS to permit the viewer to fetch your config and JSON files.

See the repository README for the full data schema and hosting guidance.
