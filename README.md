# Fractal Flame

An iterated function system, rendered by density — a flame fractal you can
steer, animate, and leave running as a screensaver.

**Live: https://laumerz84.github.io/fractal-flame/**

One self-contained HTML file. No libraries, no build step, no network. Save
`index.html` anywhere and open it, and it works offline forever.

## Screensaver

The screensaver is built in, not bolted on.

- **S** — enter screensaver. Hides every control and cross-fades to a new
  flame roughly every 90 seconds, rather than cutting.
- In the **Screensaver** panel, *Enter automatically when idle* turns on
  unattended mode. The idle delay is adjustable from 10 seconds to 10 minutes.
  It is off by default.

It is non-destructive by design: while running it cycles through mutations,
then hands your own flame back untouched when you leave. Tick *Keep the
screensaver's flame when it exits* if you want to keep what it wandered into.

## Keys

| | |
|---|---|
| **S** | screensaver |
| **F** | fullscreen |
| **H** | hide the interface |
| **A** | animate |
| **P** | save a PNG |
| **space** | pause accumulation |

## Presets

Four saved flames are in `presets/`. Each file has its name on the first line,
then JSON.

To load one: open the **JSON** panel at the bottom of the sidebar, paste the
preset in — from the opening `{`, not the name line — and press **Import**.

**Copy JSON** and **Export** go the other way, so a flame you like can be
saved back out as a file like these.

## Embedding it

To run this inside another page or an app's webview, point an iframe at it:

```html
<iframe src="https://laumerz84.github.io/fractal-flame/"
        allow="fullscreen"
        style="border:0;width:100%;height:100%"></iframe>
```

`allow="fullscreen"` matters. Without it the **F** key silently does nothing —
the browser blocks fullscreen requests from an iframe that has not been
granted it, and reports no error.

## Built with

Claude, in a browser, with no dependencies. The whole program is `index.html`.
