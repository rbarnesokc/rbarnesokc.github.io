# Fonts

Self-hosted so the page does not depend on a third-party font service, and so the heading font can be preloaded (it prevents the opening heading from reflowing when the font arrives).

Both families are latin subsets downloaded from Google Fonts and are licensed under the SIL Open Font License 1.1 (https://openfontlicense.org), which allows bundling them with a website.

| Files | Family | Designer |
| --- | --- | --- |
| `londrina-solid-300/400/900.woff2` | Londrina Solid | Marcelo Magalhães |
| `barlow-semi-condensed-400/500/600.woff2` | Barlow Semi Condensed | Jeremy Tribby (The Barlow Project) |

To add a weight, request it from `https://fonts.googleapis.com/css2?family=...` with a modern browser user agent, download the `/* latin */` woff2 file it lists, and add a matching `@font-face` rule at the top of the `<style>` block in `index.html`.
