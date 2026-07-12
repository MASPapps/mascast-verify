# mascast-verify

## Cursor Cloud specific instructions

This repository is **not an application**. It is a static host for a domain-ownership
verification asset:

- `README.md` — one-line title.
- `tiktokm913HHEacDCAIHhoDpWAgJjMytnt32c7.txt` — a TikTok developer
  domain-verification token file. It must be served at the domain root, unmodified,
  so TikTok can confirm domain ownership.

There is **no source code, no dependency manifest, no build step, and no test suite**.
Nothing needs to be installed to work in this repo. The update script is intentionally
a no-op.

### Running it

The only meaningful "run" is serving the files statically so the verification token is
reachable over HTTP. Python 3 is preinstalled:

```
python3 -m http.server 8000
```

Then the verification file is available at
`http://localhost:8000/tiktokm913HHEacDCAIHhoDpWAgJjMytnt32c7.txt` and must return the
exact contents `tiktok-developers-site-verification=m913HHEacDCAIHhoDpWAgJjMytnt32c7`.

### Gotchas

- Do not rename or edit the `tiktok...txt` file; TikTok verification depends on its exact
  path and contents.
- If real application code is added later, this file should be updated with actual
  install/build/test/run instructions.
