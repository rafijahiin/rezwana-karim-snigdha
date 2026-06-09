# Go Live + Let Rezwana Edit — Step-by-Step

This is the editable website for Dr. Rezwana Karim Snigdha. It's a fast, SEO-friendly
static site (built with **Eleventy**) plus a friendly visual editor (**Decap CMS**) so
Rezwana can change text, publications, talks, photos, etc. with **no code**.

Total time: ~15 minutes. You need two free accounts: **GitHub** and **Netlify**.

---

## Part 1 — Put the code on GitHub (~5 min)

The CMS saves edits by committing to GitHub, so the project must live in a GitHub repo.

1. Create a free account at **https://github.com** (skip if you have one).
2. Click **+ → New repository**. Name it `rezwana-karim-snigdha`. Keep it **Public**
   (or Private — both work). **Do not** add a README. Click **Create repository**.
3. Upload this project. Easiest options:

   **Option A — GitHub Desktop (no command line):** install GitHub Desktop, *Add Local
   Repository* → choose this `site` folder → *Publish repository*.

   **Option B — command line** (run inside this `site` folder):
   ```bash
   git remote add origin https://github.com/<your-username>/rezwana-karim-snigdha.git
   git branch -M main
   git push -u origin main
   ```
   (The repo is already initialised and committed — you only push.)

   > ⚠️ Don't upload the `node_modules` or `_site` folders — they're already excluded
   > by `.gitignore`. The folder has ~27 source files; that's correct.

---

## Part 2 — Deploy on Netlify (~5 min)

1. Create a free account at **https://netlify.com** → sign up **with GitHub** (simplest).
2. **Add new site → Import an existing project → GitHub →** pick `rezwana-karim-snigdha`.
3. Netlify auto-reads `netlify.toml`, so the build settings are already correct:
   - Build command: `npm run build`
   - Publish directory: `_site`
   Click **Deploy**. Wait ~1 minute → your site is live at a `something.netlify.app` URL.
4. **Rename the site** (recommended): Site configuration → *Change site name* →
   `rezwana-karim-snigdha`. Your address becomes
   **https://rezwana-karim-snigdha.netlify.app** (this matches the values already set in
   the project; if you pick a different name, update `url` in the CMS "Site content" and
   `site_url` in `src/admin/config.yml`).

---

## Part 3 — Turn on editing for Rezwana (~5 min)

1. In your site's Netlify dashboard: **Integrations / Identity → Enable Identity.**
   (On newer Netlify UIs this is under **Site configuration → Identity**.)
2. Under **Identity → Registration**, set it to **Invite only** (so only invited people
   can edit).
3. Under **Identity → Services → Git Gateway → Enable Git Gateway.** *(This is what lets
   the editor save changes — don't skip it.)*
4. **Identity → Invite users →** enter Rezwana's email (and your own). They each get an
   email → click it → set a password.
5. Rezwana logs in at **https://rezwana-karim-snigdha.netlify.app/admin/** and can edit
   everything. When she clicks **Publish**, Netlify rebuilds automatically (~1 min) and
   the change goes live.

That's it — the site is live and editable. 🎉

---

## How Rezwana edits (share this with her)

1. Go to **your-site.netlify.app/admin/** and log in.
2. Pick a section on the left: **Site/Hero/Contact, Research Areas, Publications, Talks,
   Projects, Recognition & Service, Fieldwork Map.**
3. Change text in the boxes, or click **＋** to add a publication/talk/etc., or upload a
   photo. A live preview shows on the right.
4. Click **Publish → Publish now.** Done — the website updates itself.

No HTML, no code, nothing to break. To swap her hero photo: *Site content → Hero portrait
→ choose an image.*

---

## Editing locally before going live (optional, for you)

```bash
cd site
npm install
npm start            # preview at http://localhost:8080
# In a second terminal, to test the CMS locally:
npx decap-server     # then open http://localhost:8080/admin/ and click "Login"
```

---

## Custom domain (optional)

If she buys a domain (e.g. `rezwanakarim.com`): Netlify → **Domain management → Add a
domain** → follow the DNS steps. Netlify gives a free SSL certificate automatically.
Then update `url` (CMS Site content) and `site_url` (`src/admin/config.yml`) to the new
domain for correct SEO tags.

---

## SEO — to actually rank for "anthropologist of Bangladesh"

The site already includes Person/ProfilePage structured data, meta tags, semantic
headings, and fast static pages. The rest is off-page and takes weeks:

1. **Google Search Console** + **Bing Webmaster Tools** — verify the domain, submit the
   site, request indexing.
2. **Create a Wikipedia article** for her (she's notable: PhD, books, 320+ citations,
   national grant, international keynotes). This is the single biggest lever for
   "top anthropologist" searches — have a third party write it with independent sources.
3. **Backlinks** from her Jahangirnagar & North South profiles, Google Scholar,
   ResearchGate, Academia.edu, and the University of Iowa news page → link them to this site.
4. **Press/interviews** (Prothom Alo, The Daily Star) that name her as a leading
   Bangladeshi feminist anthropologist.

A site alone can't guarantee a #1 ranking, but for this low-competition query the
combination above gives a genuinely strong shot.
