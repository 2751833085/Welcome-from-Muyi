# Advanced CC Works

The five projects from this year's Advanced Critical Computation course, part of [Welcome from Muyi](../README.md).

[Open the live page](https://2751833085.github.io/Welcome-from-Muyi/Advanced%20CC%20Pages/advanced-cc.html)

## Projects

| # | Project | Summary | Folder |
| --- | --- | --- | --- |
| I | Portfolio Website 2.0 | This website itself | [repository root](..) |
| II | Words in Motion | *Minimize*, *Procrastinate* and *Irony*, each in three P5.js motion studies, plus three final works | [`Assignment 2/`](Assignment%202) |
| III | Experimental Camera | A retro Soviet EL surveillance interface with hand-tracked interaction | [`Experimental Camera/`](Experimental%20Camera) |
| IV | Community Tool | Phantopteryx Toolbox by Oneiron v0.1.0, a lightweight browser toolbox | [`Community Tool/`](Community%20Tool) |
| V | Digital Divination | The toolbox rebuilt into a desktop-style image editing workspace on Firebase | [`Digital Divination/`](Digital%20Divination) |

## Folder notes

### Assignment 2

`sketches/` holds twelve self-contained P5.js sketches. Folders `1-x`, `2-x` and `3-x` are the three versions of each word; `Final 1` to `Final 3` are the finished pieces. Each sketch is loaded into an iframe on demand. They all share one copy of p5.js and p5.sound in `sketches/lib/`.

### Experimental Camera

`project/` is the full camera app and opens fullscreen from the project page. It needs camera permission.

| File | Role |
| --- | --- |
| `project/sketch.js` | Entry point |
| `project/src/lowResCam.js` | Low-resolution camera feed |
| `project/src/inputHand.js` | Hand tracking input |
| `project/src/screens*.js` | Boot, menu, settings and game screens |
| `project/src/state.js`, `visuals.js` | Shared state and drawing helpers |

### Community Tool and Digital Divination

Both pages describe the Phantopteryx Toolbox. The prototype kept in this repository lives in [`Phantopteryx-Toolbox/`](../Phantopteryx-Toolbox); the final version is hosted separately:

- [Live final project](https://phantopteryx-toolbox.web.app/)
- [Source repository](https://github.com/2751833085/Phantopteryx-Toolbox-by-Oneiron)

## Files

| File | Purpose |
| --- | --- |
| [`advanced-cc.html`](advanced-cc.html) | Index page with one card per project |
| [`../assets/css/pages.css`](../assets/css/pages.css) | Styles shared with the other section pages |
