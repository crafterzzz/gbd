# gbd

## Google Sites embed

`Geometry Dash.html` is the hosted HTML endpoint used by the Google Sites
embed snippet. Keep it at the repository root so the raw URL remains:

```text
https://raw.githubusercontent.com/crafterzzz/gbd/main/Geometry%20Dash.html
```

After committing and pushing the file to `main`, set the snippet's
`RAW_HTML_URL` to that URL. In Google Sites, add the snippet with **Insert >
Embed > Embed code**, then publish the Site and test the published page.

The HTML loads the game's other files from the pinned `raw.githubusercontent.com`
base URL in its `<base>` element. That upstream snapshot must remain available.
If you move those assets into this repository, update the `<base>` URL to the
new asset root and preserve their directory layout.

The Sites snippet sets `indexedDB` to `null` for an opaque origin. The hosted
HTML therefore skips save restoration and save requests when IndexedDB is
unavailable; game saves will not persist in that case. The browser console
will warn that saves are disabled.