# WoW!Lab Preview Cloud

This folder is the static library root for GitHub Pages.

Expected published structure:

```text
manifest.json
previews/*.json
covers/*.png
```

Workflow:

1. Add a preview JSON to `previews/`.
2. Add its cover image to `covers/` using the same stem when possible.
3. Run:

```powershell
& 'C:\Users\Kutsushita\AppData\Local\Python\bin\python.exe' tools\build_preview_cloud_manifest.py
```

4. Upload or commit the contents of `preview_cloud/` to the GitHub Pages repository.
5. Put the published manifest URL into `preview_library_manifest_url`, for example:

```text
https://username.github.io/wowlab-preview-cloud/manifest.json
```

The app downloads `manifest.json` first, caches covers in `lib/cache/covers`, and downloads full preview JSON files only when the user clicks `Download`.

Collections live in `manifest.json`:

```json
{
  "id": "starter_wow",
  "title": "Стартовые превью",
  "items": ["figure_x1_wow", "decor_fence_x1_wow"]
}
```

One preview can be used in multiple collections because collections only store preview ids.

Owner uploader:

```powershell
& 'C:\Users\Kutsushita\AppData\Local\Python\bin\python.exe' tools\preview_cloud_uploader.py
```
