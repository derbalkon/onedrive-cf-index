# OneDrive Index

[![Hosted on Cloudflare Workers](https://img.shields.io/badge/Hosted%20on-CF%20Workers-f38020?logo=cloudflare&logoColor=f38020&labelColor=282d33)](https://storage.spencerwoo.com/)
[![Deploy](https://github.com/derbalkon/onedrive-cf-index/workflows/Deploy/badge.svg)](https://github.com/derbalkon/onedrive-cf-index/actions?query=workflow%3ADeploy)

> This project is forked from [spencerwoo/onedrive-cf-index](https://github.com/spencerwooo/onedrive-cf-index), greatly inspired by [onedrive-index-cloudflare-worker](https://github.com/heymind/OneDrive-Index-Cloudflare-Worker).

## Features

### General

- Breadcrumbs for better navigations.
- Tokens cached and automatically refreshed with Cloudflare Workers KV storage.
- Route lazy loading with the help of [Turbolinks®](https://github.com/turbolinks/turbolinks).

### Folder indexing

- Complete new and customisable design at [spencer.css](themes/spencer.css).
- Emoji as folder icon when available (if the first character of the folder name is an emoji).
- Renders `README.md` if found in current folder. Rendered with [github-markdown-css](https://github.com/sindresorhus/github-markdown-css).
- Supports pagination, no more limitations like 200 items max for each folder ever again!

### File previews

- File icon rendered according to file type, [Font Awesome icons](https://fontawesome.com/) for cleaner look.
- Plain text: `.txt`.
- Markdown: `.md`, `.mdown`, `.markdown`.
- Image, supports Medium style zoom effect: `.png`, `.jpg`, and `.gif`.
- Code with syntax highlighting: `.js`, `.py`, `.c`, `.json`, etc.
- PDF: Lazy loading, loading progress and built-in PDF viewer.
- Music / Audio: `.mp3`, `.aac`, `.wav`, `.oga`.
- Videos: `.mp4`, `.flv`, `.webm`, `.m3u8`.

### Proxied / raw file download

- [Optional] Proxied download: `?proxied` - Downloads the file through CloudFlare Workers if (1) `proxyDownload` is true in `config/default.js` and (2) parameter is present in url.
- [Optional] Raw file download: `?raw` - Return direct raw file instead of rich rendered preview if parameter is present.
- Both these parameters can be used side by side, meaning that `?proxied&raw` and `?raw&proxied` are both valid.

Yes, this means you can use this project as an image storage service or for serving static files, for example:

```text
https://storage.spencerwoo.com/%F0%9F%A5%9F%20Some%20test%20files/nyancat.gif?raw
```

![example](https://storage.spencerwoo.com/%F0%9F%A5%9F%20Some%20test%20files/nyancat.gif?raw)

---

## Credit

- **Heymind** for [original project](https://github.com/heymind/OneDrive-Index-Cloudflare-Worker).
- **Spencerwoo** for [maintaining](https://github.com/spencerwooo/onedrive-cf-index).
