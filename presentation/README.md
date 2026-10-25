# Slides

The presentation is [`workshop.md`](workshop.md), written in [Marp](https://marp.app/) Markdown.
Speaker notes are the `<!-- ... -->` comments under each slide.

## Present / edit

- **VS Code:** install the *Marp for VS Code* extension, open `workshop.md` and click the preview icon.
  Enable *Markdown › Marp: Enable HTML* in the settings (the deck uses a bit of HTML for two-column layouts).
- **Browser:** export to HTML (below) and open it. Press `F` for fullscreen and `P` for the presenter view with notes.

## Export (no Node.js needed, we use Docker of course 🐳)

Run these from this `slides/` folder:

```bash
# HTML (best for presenting: presenter view with notes)
docker run --rm --init -v "$PWD:/home/marp/app" -e MARP_USER="$(id -u):$(id -g)" \
  marpteam/marp-cli workshop.md --html --allow-local-files -o workshop.html

# PDF (for sharing)
docker run --rm --init -v "$PWD:/home/marp/app" -e MARP_USER="$(id -u):$(id -g)" \
  marpteam/marp-cli workshop.md --html --allow-local-files --pdf -o workshop.pdf
```

With Node.js installed you can use `npx @marp-team/marp-cli workshop.md --html --allow-local-files` instead.

## Diagrams

`assets/*.svg` are hand-written SVG files, so you can edit them in any text editor or in Inkscape.
