# Ad Studio Demo

A small prototype of a template-based ad creation engine. One template renders in two ad sizes (300×250 display and 1080×1350 Meta feed), with a live preview that updates as you edit.

It shows the core idea behind a branded ad platform: clients can change the content, but the design stays locked.

## What it demonstrates

- **Locked templates.** Layout, fonts and element positions are fixed. Clients only edit named slots: headline, offer, button text, brand color and logo.
- **A layout per size.** Each size has its own layout instead of scaling one design up or down, so small banners stay readable.
- **Live preview.** Rendered in the browser with [Konva.js](https://konvajs.org/) on a canvas.
- **Automatic contrast.** Text and button colors switch between light and dark depending on the brand color.
- **Text limits.** Long headlines are clipped inside their box so they can't break the design.

## Run it

No build step. Open `index.html` in a browser. It loads Konva and fonts from a CDN, so you need an internet connection.

## Publish it with GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute, the demo is live at `https://<your-username>.github.io/<repo-name>/`.

## How it works

Each size is described by a layout object with positions for the photo area, logo, headline, offer badge and button. A single `draw()` function renders any layout from the same content values, so adding a new size means adding one layout object.

```js
const LAY = {
  a: { w: 300, h: 250, head: { x: 16, y: 62, w: 146, h: 84, fs: 24 } /* ... */ },
  b: { w: 1080, h: 1350, head: { x: 72, y: 750, w: 936, h: 300, fs: 92 } /* ... */ },
};
```

## Scope

This is a front-end prototype of the template and preview approach. It does not include accounts, saved projects, server-side export, payments, or website scanning.

## Possible next steps

- Add the remaining sizes (728×90, 300×600, 336×280, 320×50, 1080×1350, 1080×1920).
- Render the same template on the server for downloads that match the preview.
- Move template layouts into JSON so non-developers can add them.
- Add accounts, roles, payments and AI-assisted content from a website URL.

## Stack

HTML, JavaScript, Konva.js

## Author

Awais Rehman
