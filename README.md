# openRxiv Labs

Source for the [openRxiv Labs](https://openrxivlabs.org) landing pages and blog.

The content is authored in [MyST Markdown](https://mystmd.org) and managed with [Curvenote's Scientific Content Management System (SCMS)](https://curvenote.com/products/scms). Pull requests automatically build a preview of any blog content, and merges to `main` publish the landing pages and any blog posts that have changed.

## Repository layout

- `landing/` — the openRxiv Labs landing site (`index.md`, `faq.md`, `myst.yml`). Published on push to `main`. There is no preview environment for the landing pages today; review changes locally before merging.
- `blog/<slug>/` — one folder per blog post. Each post has its own `myst.yml` with a unique `id` (UUID) that identifies the work in Curvenote's database.
- `authors.yml` — shared authors, affiliations, venue, and abbreviations used by blog posts.
- `.github/workflows/` — Curvenote GitHub Actions that draft previews on PRs and publish on merge to `main`.

## Authoring locally

You can preview content with either MyST or the Curvenote CLI. Run the command from inside the folder you want to preview (`landing/` or a specific `blog/<slug>/`).

### MyST

```bash
pip install mystmd

cd landing            # or: cd blog/<slug>
myst start
```

### Curvenote

```bash
npm install -g curvenote

cd landing            # or: cd blog/<slug>
curvenote start
```

Frontmatter and Markdown syntax are documented at [mystmd.org](https://mystmd.org). Deployment and CLI usage for Curvenote are documented at [docs.curvenote.com/publish/cli-overview](https://docs.curvenote.com/publish/cli-overview).

## How publishing works

### Pull requests

When you open a PR that touches a `blog/<slug>/` folder, the Curvenote GitHub Action drafts a preview and posts a comment on the PR with:

- a link to preview the rendered content, and
- feedback from automated content and editorial checks.

The preview updates as you push new commits to the PR.

### Merging to `main`

- Changes under `landing/` are published to the live landing site.
- Changes under `blog/<slug>/` are submitted and published to the Labs venue.

Both flows run via the Curvenote actions configured in `.github/workflows/` and use the `CURVENOTE_TOKEN` repository secret.

## Adding a new blog post

1. Copy an existing folder under `blog/` to a new slug, e.g. `blog/2026-06-01-my-post/`.
2. Open the new folder's `myst.yml` and update the metadata (title, description, authors, date, etc.).
3. **Generate a new UUID for `project.id`.** This UUID is the key for the work in Curvenote's database — reusing an existing one will collide with another post. You can generate one with `uuidgen` (macOS/Linux) or `python -c "import uuid; print(uuid.uuid4())"`.
4. Edit the content files (typically `index.md`) and open a PR. The PR comment will link to a live preview once the draft action finishes.

## Publishing a blog post

After a blog post has been merged to `main` and submitted, publish it from the Curvenote SCMS:

1. Open the [openRxiv Curvenote SCMS](https://openrxiv.curvenote.com).
2. Go to **Sites**, select **labs**, and press **Publish** on the submission.

You can also reach this screen directly from the editorial views on the preview pages.

Before publishing, ensure the **slug** is set correctly in the SCMS — it may differ from the folder name in this repository.
