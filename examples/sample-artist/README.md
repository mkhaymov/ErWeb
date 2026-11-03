# Sample artist data package

This folder demonstrates the data files an artist can host for the shared ErWeb viewer. Its config and JSON files are sample data; the displayed sample images are fetched directly from Wikimedia Commons and are not hosted by this repository. Attribution/source notes are in [`images/README.md`](images/README.md).

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

Copy this folder to a location you control, update `config.json` with your own brand and data URLs, and update the gallery and artwork JSON with your content. Replace the sample image URLs with URLs to images you host. For a separate domain, configure CORS to permit the viewer to fetch your config and JSON files.

See the repository README for the full data schema and hosting guidance.
