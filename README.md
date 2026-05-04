# First Aid Swipe File

A calm, scannable, single-page first aid reference with embedded Red Cross video refreshers. Designed for quarterly self-review between proper first aid courses.

**Live demo:** *(add your GitHub Pages URL once deployed)*

## What this is

A static HTML page covering twelve common first aid scenarios — CPR, AED use, choking, severe bleeding, burns, shock, anaphylaxis, seizure, heat stroke, hypothermia, sprains, and poisoning. Each card opens a panel with summarized steps, a "what to avoid" list, and an embedded video from the American or British Red Cross.

No build step. No tracking. No dependencies. One HTML file, ~800 lines.

## What this is not

Not a substitute for actual first aid training. Take a real Red Cross or equivalent course at least once. This is the page you open between courses for a five-minute refresher.

## Deploying to GitHub Pages

1. Create a new public repo (for example, `first-aid-swipe-file`).
2. Add `index.html` (and optionally `README.md`, `LICENSE`) at the repo root.
3. In the repo settings, go to **Pages** in the sidebar.
4. Under **Source**, pick **Deploy from a branch**, then select `main` and `/ (root)`.
5. Save. Within a minute or two, the page will be live at `https://<your-username>.github.io/<repo-name>/`.

That's it. No build, no Actions config, no framework.

## Embedding in another site

The page is iframe-friendly. To embed it in `amit.sh` (or anywhere else):

```html
<iframe
  src="https://<your-username>.github.io/first-aid-swipe-file/"
  title="First Aid Swipe File"
  style="width: 100%; height: 1200px; border: 0; border-radius: 12px;"
  loading="lazy"
></iframe>
```

Adjust the height to taste. The page is responsive, so the iframe can be any width.

## Customizing

All scenarios live in the `scenarios` array near the bottom of `index.html`. Each entry has:

- `id` — unique slug
- `category` — `core`, `outdoor`, or `home` (drives the filter chips)
- `severity` — `critical`, `urgent`, or `standard` (drives the colored dot)
- `title`, `summary`, `when911`
- `steps` — array of step strings (HTML allowed for `<strong>` and `<em>`)
- `donts` — array of "avoid" strings
- `video` — `{ id, title, source, url }` where `id` is the YouTube video ID

To add a scenario, copy an existing object and edit. To change the look, the CSS variables at the top of the `<style>` block control the entire palette.

## Why these specific videos

Sources are the **American Red Cross** YouTube channel where available, the **British Red Cross** for topics where the ARC doesn't have a current short-form video (burns, hypothermia, seizures, sprains). The poisoning card intentionally has no embedded video and instead surfaces the US Poison Control number, since calling them is the correct action and they walk you through everything.

## License

MIT. Use it, fork it, embed it, ship it. See `LICENSE`.

The Red Cross videos themselves remain the property of their respective organizations and are embedded using YouTube's public embed system.

## Disclaimer

This page is a study aid, not medical advice. In any real emergency, call 911 (or your local equivalent) and follow the dispatcher's instructions. The author is not a medical professional. Information is summarized from publicly available Red Cross materials but is not a substitute for proper certification.
