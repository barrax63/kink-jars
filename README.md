# Kink Jars

A single-page questionnaire: pick a color, rate each jar 1–5 (or tag it curious, or tape it shut as a hard limit), save a PNG.
Everything runs in the browser. Nothing is uploaded, and answers are only kept in that person's browser (localStorage) so a refresh doesn't wipe them.
The page makes no third-party requests: the fonts are served from the `fonts/` folder, not from Google Fonts.

## Compare, or load a saved picture

A saved picture is its own save file: the page can read the jars and the color back out of it, right in the browser.

- **Compare with someone:** add a picture they saved. Each jar splits in two, yours on the left and theirs on the right, and a heart marks every jar you both rated 4 or 5. Give/receive jars are matched across (your "spanking" sits next to their "being spanked"). Their answers are held in memory only and are gone on refresh.
- **Load my own saved picture:** puts the jars and color from a saved picture back on the page. The name is not read back, except from a file name like `sam-kink-jars.png`.

It needs the whole picture, at least 600px wide; pictures sent through a messenger are fine, crops and screenshots are refused. Comparison pictures cannot be loaded back.

## Host it free on GitHub Pages

1. Create a new repo (public is required for free Pages) and add `index.html` and the `fonts/` folder.
2. Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**, pick `main` / `(root)`, Save.
3. After a minute it's live at `https://<your-username>.github.io/<repo-name>/`.

Netlify Drop or Cloudflare Pages work too: drag the folder in, done.

## Customizing

- **Jar labels:** edit the `JARS` array at the top of the `<script>`. Each entry is a list of label lines. The grid is 7 columns wide and grows rows as needed.
- **Give/receive pairs:** `PAIRS` lists which jars are two sides of one thing, by their position in `JARS`. Keep it in step when you reorder jars.
- **Preset colors:** edit `PRESETS`.
- **Overflow looks:** six styles (drips, puddle, foam with popped lid, geyser, splash, hearts), assigned so neighbors never match. Details are seeded per jar, so every friend's sheet is consistent.
