# Prateek Bhardwaj — personal site

Plain HTML/CSS/JS. No build step, no npm, no framework. Preview by double-clicking
`index.html`, deploy in a couple minutes via GitHub Pages, Vercel, or Netlify.

## Structure

- **Blog** — longer write-ups on things you've built or worked through.
- **Notes** — rough, unstructured notes on things you're learning. No polish required.
- **Resume** — plain HTML, edit directly.

## File map

```
index.html            → home page (bio + combined recent feed)
blog.html              → blog listing (reads BLOG_POSTS from assets/data.js)
notes.html             → notes listing (reads NOTES from assets/data.js)
resume.html            → resume, editable directly in HTML
assets/style.css       → all styling, one file
assets/data.js         → BLOG_POSTS and NOTES arrays live here
blog/_template.html    → copy this to start a new blog post
notes/_template.html   → copy this to start a new note
blog/*.html, notes/*.html → individual pages
```

## Adding a blog post

1. Copy `blog/_template.html` → rename to `blog/your-slug.html`.
2. Edit the title, date, `<h1>`, and body.
3. Add an entry to the top of `BLOG_POSTS` in `assets/data.js`:

```js
{
  slug: "your-slug",         // must match the filename
  title: "Post title",
  excerpt: "One or two sentences for the listing page.",
  date: "2026-09-01",
  tags: ["python", "backend"]
}
```

## Adding a note

Same idea, but in `notes/`:

1. Copy `notes/_template.html` → rename to `notes/your-slug.html`.
2. Write it rough — that's the point.
3. Add an entry to the top of `NOTES` in `assets/data.js`:

```js
{
  slug: "your-slug",
  title: "Note title",
  excerpt: "One line for the listing page.",
  date: "2026-09-01",
  tags: ["distributed-systems"]
}
```

Save both files, refresh — no build step, it just shows up on the home page,
the section listing, and its own page.

## Previewing locally

Open `index.html` directly in a browser — no local server required.

## Deploying to GitHub Pages

1. Create a repo named exactly `<your-username>.github.io` (for the root URL),
   or any name (for a `/reponame/` URL).
2. From inside this folder:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

3. Repo → Settings → Pages → source should default to "Deploy from a branch",
   branch `main`, folder `/ (root)`. Save if needed.
4. Visit `https://<your-username>.github.io` (or `.../reponame/`) after ~1 minute.

## Deploying to Vercel or Netlify

Both support dragging this folder onto their dashboard for an instant static
deploy, and both handle custom domains + SSL automatically once you point
your domain's DNS at them.
