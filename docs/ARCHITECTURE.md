# Architecture

How [Welcome from Muyi](../README.md) is put together. The site is plain HTML, CSS and JavaScript with no build step.

## Page shell

Every page follows the same pattern:

1. `<html class="is-loading">` hides the entry animations until the page is ready.
2. [`assets/js/loader.js`](../assets/js/loader.js) is loaded from `<head>` and decides how the page appears.
3. When the loader plays, the same script waits for fonts and page resources (at least 1.2 s, at most 4.2 s) and then fades it out. Pages need no script of their own for this.

## Loader and page transitions

`loader.js` picks one of two paths before the first paint:

| Situation | What happens |
| --- | --- |
| Entering the site, typing a URL, or refreshing | The lemniscate particle loader plays, then fades out |
| Following a link inside the site, or using back/forward | No loader; the browser cross-fades between pages and the page plays its own entrance animation |

It tells the two apart with the navigation type, a same-origin referrer check, and a `sessionStorage` flag set when an internal link is clicked (which keeps it working from `file://`).

The cross-fade is a native cross-document view transition, enabled by an `@view-transition` rule the script injects. Browsers without support get a short fade-in instead. Both are skipped when the system asks for reduced motion.

## Navigation

All navigation uses ordinary `<a href>` links. A speculation-rules block in each page's `<head>` prefetches internal links on hover.

## Styles

- [`assets/css/home.css`](../assets/css/home.css) styles the home page: a viewport-proportional desktop layout over the hero artwork, and a card layout below 47.5em.
- [`assets/css/pages.css`](../assets/css/pages.css) holds everything the section pages share: layout, cards, the back link, buttons.
- A section only keeps its own stylesheet when it has rules nobody else uses (`cc-lab.css`, `assignment2.css`, `digital-divination.css`). It is loaded after `pages.css`.
- Font sizes use `rem` and `clamp()` so they follow browser and OS text-size settings.
- Hover underlines on links are drawn with a background gradient that grows from the left.

## Images

The hero artwork is served through `<picture>`: WebP at two sizes with the original PNG as a fallback. On the mobile layout a 1×1 placeholder is selected, so the artwork is not downloaded.

## Local development

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.
