# puhu.registry

Central plugin registry for [Puhu](https://github.com/st0o0/puhu). The Puhu Marketplace fetches `index.json` to discover available plugins.

## Adding Your Plugin

1. Create a GitHub repo for your plugin
2. Add a `puhu-manifest.json` manifest to the repo root (on `main` branch)
3. Open a PR to this repo adding your plugin to `index.json`

### `index.json` Entry Format

```json
{
  "id": "your.plugin.id",
  "repository": "https://github.com/your-org/your-plugin"
}
```

### `puhu-manifest.json` Manifest

Your plugin repo must contain this file at the root of the `main` branch:

```json
{
  "id": "your.plugin.id",
  "name": "My Plugin",
  "description": "What it does",
  "author": "your-name",
  "version": "1.0.0",
  "minPuhuVersion": "1.0.0",
  "license": "MIT",
  "repository": "https://github.com/your-org/your-plugin",
  "delivery": {
    "type": "github-release",
    "asset": "Your.Plugin.dll"
  },
  "tags": ["category"]
}
```

### Delivery Types

- `github-release` — DLL published as a GitHub Release asset (`asset` field required)
- `nuget` — NuGet package (`packageId` field required, not yet implemented)
