# reveal-lite

A minimal fork of [reveal.js](https://revealjs.com/) (v6.0.1) for creating and serving browser-based slide presentations written in Markdown.

## How it works

Write your slides in a `.md` file using plain Markdown. Horizontal slides are separated by three blank lines; vertical slides by two. Each presentation lives in its own folder alongside an `index.html` that loads it.

Each folder contains exactly two files:

```
my-talk/
  index.html    # presentation entry point
  my-talk.md    # your slide content
```

Inside `index.html`, the `data-markdown` attribute on the `<section>` element must match the name of the `.md` file in that folder:

```html
<section data-markdown="my-talk.md" ...></section>
```

## Running locally

Start a local HTTP server from the repo root:

```bash
python3 -m http.server
```

Then open `http://localhost:8000/my-talk/index.html` in a browser.

## Slide format

```markdown
# Slide title
First horizontal slide content


## Second slide
Two blank lines above = new horizontal slide


## Vertical slide
One blank line above = slide below the previous one


Note:
Speaker notes go here (not visible to the audience)
```

## Customisation

- **Theme** — swap `dist/theme/sky.css` in `index.html` for any other theme in `dist/theme/`
- **Styling tweaks** — edit `asset/style/tweak.css`
- **Presentation config** — adjust width, height, transition, and plugins in the `Reveal.initialize()` call inside `index.html`

## Hosting on GitHub Pages

The presentation works as-is when served from GitHub Pages. Point Pages at the repo root and navigate to `/my-talk/index.html`.
