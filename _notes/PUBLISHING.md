# Publishing notes (for Caleb)

This file is your own reference for building and deploying the site. It isn't meant for a visitor to the repo — that's what README.md is for.

---

## Three files you need to add before rendering

1. `images/headshot.jpg` — save the photo from your current site (right-click → Save Image As)
2. `cv/schmotter-cv.pdf` — your current CV
3. `files/psc-1000-tyrants-demagogues-and-democrats.pdf` — the sample syllabus

Optional: `images/favicon.png` (small square image for the browser tab). If you skip it, delete the `favicon:` line in `_quarto.yml`.

---

## Step 1 — Preview it on your Mac

You almost certainly already have Quarto via RStudio. Check in Terminal:

```bash
quarto --version
```

If that errors, download the installer from quarto.org.

Then, from inside this folder:

```bash
quarto preview
```

A browser window opens with the live site. Leave it running — every time you save a `.qmd` file, the page refreshes automatically.

Press `Ctrl+C` in Terminal to stop.

---

## Step 2 — Put it on GitHub

1. Create a free account at github.com.
2. Click **+** (top right) → **New repository**. Name it `website`. Don't add a README — you already have one.

   **Public or Private?** If you go Public, anyone can browse this entire folder at github.com, including this file, even though none of it renders on the live site (only `docs/` does). Nothing in here is sensitive, but worth knowing before you pick. Private repos can also publish Pages, though double-check GitHub's current free-tier terms for that at the time you set this up, since those policies shift.

3. On the next screen, click **uploading an existing file**.
4. Drag this entire folder's contents into the browser window. Click **Commit changes**.

That's it — no command line needed for this part.

---

## Step 3 — Turn on GitHub Pages

1. In your repository, click **Settings** → **Pages** (left sidebar).
2. Under "Build and deployment," set Source to **Deploy from a branch**.
3. Set branch to `main` and folder to `/docs`. Click **Save**.

Wait about a minute. Your site is live at `https://YOURUSERNAME.github.io/website/`.

> **Important:** for this to work you must run `quarto render` before uploading, so the `docs/` folder exists.

---

## Step 4 — Point calebschmotter.com at it

Only do this once you're happy with the new site. Your WordPress stays up untouched until you switch.

1. In your repo: **Settings → Pages → Custom domain**. Enter `calebschmotter.com`. Save.
2. At your domain registrar, add these DNS records:

   **A records** for `@` pointing to:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

   **CNAME record** for `www` pointing to `YOURUSERNAME.github.io`

3. Back in GitHub Pages settings, tick **Enforce HTTPS** once it becomes available (can take an hour).

DNS changes take anywhere from a few minutes to a day.

---

## Making changes later

Edit the `.qmd` file → run `quarto render` → upload the changed files to GitHub. Or edit directly in GitHub's web interface if it's just a text tweak (but then you'd need to re-render, so local is simpler).

**Adding a publication:** copy an existing `::: {.entry}` block in `research.qmd` and change the text.

**Changing colors:** open `styles.scss`. The palette is the first eight lines.
