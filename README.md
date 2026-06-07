# memotify-pages

Public GitHub Pages host for [Memotify](https://github.com/wakatakerutmt/memotify) (the app repo is private).

Serves the in-app legal pages — Terms of Service and Privacy Policy — that the Paywall screen links out to.

## Live URLs

- <https://wakatakerutmt.github.io/memotify-pages/legal/terms.ja/> — 利用規約 (JP)
- <https://wakatakerutmt.github.io/memotify-pages/legal/terms.en/> — Terms of Service (EN)
- <https://wakatakerutmt.github.io/memotify-pages/legal/privacy.ja/> — プライバシーポリシー (JP)
- <https://wakatakerutmt.github.io/memotify-pages/legal/privacy.en/> — Privacy Policy (EN)

## Local preview

```bash
bundle install
bundle exec jekyll serve
# → http://127.0.0.1:4000/memotify-pages/
```

## Layout

```
memotify-pages/
├── _config.yml          Jekyll config (baseurl = /memotify-pages)
├── _layouts/legal.html  Shared HTML shell with dark-mode CSS + lang switcher
├── index.md             Landing page that lists the 4 legal docs
├── legal/
│   ├── terms.ja.md
│   ├── terms.en.md
│   ├── privacy.ja.md
│   └── privacy.en.md
└── Gemfile              Pinned to GitHub Pages' gem versions
```

## How it's wired to the app

The Memotify app (`lib/utils/legal_urls.dart`) picks `.ja` or `.en` based on the device locale and opens these URLs via `url_launcher`. Any structural change here — renaming a page, moving the legal/ directory — must be mirrored in that helper.

## License

The legal text is for Memotify only. Don't copy-paste verbatim for another app without your own legal review.
