# Kink Jars

A single-page questionnaire: pick a color, rate each jar 1–5 (or tag it curious, or tape it shut as a hard limit), share a link.
Everything runs in the browser. Nothing is uploaded, and answers are only kept in that person's browser (localStorage) so a refresh doesn't wipe them. A shared link carries the sheet after the `#`, a part of the address browsers never send to the host.
The page makes no third-party requests: the fonts are served from the `fonts/` folder, not from Google Fonts.

## Share and compare

There is no image to save. "Share my link" gives a link that holds the name, the color and every jar.

- **Opening a link** shows that sheet read-only, as a vector picture drawn on the spot, with a "Want to create your own? Click here" footer underneath.
- **Compare with someone:** press "Compare with mine" on their picture, or paste their link into the compare box. That opens a second read-only picture with its own link: each jar split in two, yours on the left and theirs on the right, a heart on every jar you both rated 4 or 5. Give/receive jars are matched across (your "spanking" sits next to their "being spanked"). The comparison link holds both sheets, so whoever opens it sees the same picture. It is a snapshot: change your jars and you need to compare again.
- **Use them as my own jars:** under someone's picture, this copies the sheet onto the page as your own. Handy for moving your jars to another device with your own link.

Sheets from a link are never stored. Anyone who has a link can read every sheet in it, and a comparison link gives away both.

## Host it free on GitHub Pages

1. Create a new repo (public is required for free Pages) and add `index.html` and the `fonts/` folder.
2. Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**, pick `main` / `(root)`, Save.
3. After a minute it's live at `https://<your-username>.github.io/<repo-name>/`.

Netlify Drop or Cloudflare Pages work too: drag the folder in, done.

## Customizing

- **Jar labels:** edit the `JARS` array at the top of the `<script>`. Each entry is a list of label lines. The grid is 7 columns wide and grows rows as needed.
- **Explainers:** `ABOUT` holds the one-line text behind each "What's this?" link, keyed by the jar's label. A jar without an entry simply gets no link.
- **Give/receive pairs:** `PAIRS` lists which jars are two sides of one thing, by their position in `JARS`. Keep it in step when you reorder jars.
- **Changing the set starts everyone fresh.** Answers and links are stored by position, so after adding, removing or reordering jars, bump `STORE` and the format digit in `pack` and `unpack`. Saved answers and links from the old set are then dropped instead of landing on the wrong jars. The current set has 35 jars (storage `kinkjars-v2`, link format `2`).
- **Preset colors:** edit `PRESETS`.
- **Overflow looks:** six styles (drips, puddle, foam with popped lid, geyser, splash, hearts), assigned so neighbors never match. Details are seeded per jar, so every friend's sheet is consistent.
