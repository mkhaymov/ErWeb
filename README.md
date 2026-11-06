# Artist data JSON contract

ErWeb can load artist data from JSON files hosted alongside the site or at a separate static URL. Pass the URL of the artist's `config.json` file using the `config` query parameter:

```text
https://<erweb-site>/index.html?config=<URL-encoded-config-json-url>
```

For local development, serve the repository over HTTP and pass a relative config path, for example:

```text
http://localhost:8000/index.html?config=path/to/artist/config.json
```

The config JSON supports these properties:

| Property | Required | Description |
| --- | --- | --- |
| `brandName` | No | Display name and document title. Alias: `brand_name`. |
| `logoUrl` | No | Logo URL. Alias: `logo_url`. Defaults to `logo.jpeg` relative to the config file. |
| `galleriesUrl` | No | URL of the galleries JSON. Alias: `galleries_url`. Defaults to `galleries.json` relative to the config file. |
| `imagesUrl` | No | URL of the artwork images JSON. Alias: `images_url`. Defaults to `images.json` relative to the config file. |
| `homePageUrl` | No | Home page URL. Alias: `home_page_url`. Defaults to `index.html` relative to the config file. |
| `galleryPageUrl` | No | Gallery page URL. Alias: `gallery_page_url`. Defaults to `gallery.html` relative to the config file. |
| `searchPlaceholder` | No | Search input placeholder text. Alias: `search_placeholder`. |

Example `config.json`:

```json
{
  "brandName": "Example Artist",
  "logoUrl": "assets/logo.jpg",
  "galleriesUrl": "galleries.json",
  "imagesUrl": "images.json",
  "homePageUrl": "index.html",
  "galleryPageUrl": "gallery.html",
  "searchPlaceholder": "Search artwork..."
}
```

`galleriesUrl` must point to a JSON array of gallery objects. Each object can include:

| Property | Description |
| --- | --- |
| `title` | Gallery title. |
| `coverUrl` | Gallery cover image URL, resolved relative to the galleries JSON URL. |
| `searchCriteria` | Search term used when the gallery is opened. |

Example `galleries.json`:

```json
[
  {
    "title": "Oil Paintings",
    "coverUrl": "images/oil-001.jpg",
    "searchCriteria": "oil"
  }
]
```

`imagesUrl` must point to a JSON array of artwork objects. The gallery page uses the `url`, `title`, `year`, `medium`, `dimensions`, and `keywords` fields; artwork image URLs are resolved relative to the images JSON URL. Other fields, such as `technic`, may be included as additional metadata.

Example `images.json`:

```json
[
  {
    "url": "images/oil-001.jpg",
    "title": "Example painting",
    "year": "2024",
    "medium": "Oil on canvas",
    "dimensions": "30 x 24 in",
    "keywords": "painting, landscape, oil"
  }
]
```

Relative file references are resolved from the URL of the JSON file that contains them. For example, with `galleriesUrl` set to `https://artist.example/data/galleries.json`, a cover URL of `images/cover.jpg` resolves to `https://artist.example/data/images/cover.jpg`. Make sure the hosting server allows ErWeb to fetch the JSON and image files (including cross-origin requests when the package is hosted on another domain).
