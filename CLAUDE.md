# blog.thezdev.com

The blog for The Z Dev, Michael Milford's Zoho consulting business for small businesses and nonprofits. Readers are prospective clients: owners and operators, not developers. Astro static site, deployed to GitHub Pages at https://blog.thezdev.com.

This is not the main business site. thezdev.com will be its own site later; don't link to it until it exists.

## Writing a post

- One Markdown file per post in `src/content/posts/`. The file name is the URL: `zoho-one-vs-crm-plus.md` publishes at `/posts/zoho-one-vs-crm-plus/`. Use short lowercase slugs and don't rename a file once it's published (that breaks links).
- Frontmatter: `title`, `description` (one or two sentences; used on the home page, in search results, and in link previews), `date` (YYYY-MM-DD), optional `updated`, `tags` (a short list, reuse existing tags), `draft`.
- `draft: true` keeps a post off the live site. Note the repo is public, so drafts are readable on GitHub.
- `src/content/posts/example-post.md` shows every formatting option. It stays a draft.
- Images go in `public/images/` and are referenced as `/images/name.png`. Always write alt text.

## Voice

Michael's voice rules apply to every post:

- Plain, direct, conversational. Short over long. Write for a business owner, not an engineer; explain Zoho terms the first time they come up.
- No corporate buzzwords, no boilerplate, no "it's not X, it's Y", no rule-of-three flourishes, no "in today's landscape".
- No em dashes.
- Evidence over enthusiasm: no invented metrics, no unsupported comparisons, no overclaiming. If a number or client story isn't confirmed by Michael, ask.
- Never name BusinessNext clients or describe BusinessNext client work. Zoho-era customers only with Michael's say-so.
- No call to action or contact method yet (Michael's call, 2026-11-17). Don't add one until he asks.

## Build and publish

```bash
npm install
npm run dev      # local preview at localhost:4321, drafts included
npm run build    # production build into dist/, drafts excluded
```

Push straight to `main`; no pull requests. Every push to `main` deploys (`.github/workflows/deploy.yml`), so run `npm run build` first and check the post renders. Look at a screenshot of any new post in light and dark mode and at phone width before pushing.
