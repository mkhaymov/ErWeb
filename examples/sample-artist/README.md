# Sample artist data package

This package demonstrates the viewer's configuration and data format with a neutral, generic portfolio presentation. It is not a real artist's portfolio, and the sample images are third-party works or historical photographs loaded directly from Wikimedia Commons—not artwork by the sample artist. Sources and rights notes are in [`images/README.md`](images/README.md).

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

Copy this folder to a location you control, update `config.json` with your own brand and data URLs, and replace the example gallery and artwork entries with your own content and image URLs. For a separate domain, configure CORS to permit the viewer to fetch your config and JSON files.

See the repository README for the full data schema and hosting guidance.
