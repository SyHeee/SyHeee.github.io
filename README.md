# syheee.github.io

Personal site, built with [Hugo](https://gohugo.io/) + [PaperMod](https://github.com/adityatelange/hugo-PaperMod), deployed via GitHub Actions to GitHub Pages.

## Local preview

```bash
brew install hugo               # once
git clone --depth 1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod # if missing
hugo server -D                  # -D includes drafts; serves at http://localhost:1313
```

## Writing

```bash
hugo new content posts/my-post-title.md     # learning notes
hugo new content writing/my-story.md        # fiction
```

New content starts as `draft: true`; set it to `false` to publish. The deployment workflow currently sits at the repository root; GitHub Actions only discovers it under `.github/workflows/`. No deployment configuration was changed as part of the homepage update.

## Homepage content

- `content/_index.md`: About Me, Publications, Research & Projects, Experience & Education, and Writing.
- `layouts/home.html`: PaperMod homepage override; uses the existing theme header, footer, colors, and social icons.
- `assets/css/extended/home.css`: homepage spacing.
- `hugo.yaml`: metadata, social links, and navigation.
- `content/research.md`, `content/projects.md`: existing detail URLs.
- `content/posts/` and `content/writing/`: technical notes and other writing.

Only add publication details and project summaries once verified and public. The homepage intentionally omits unprovided dates, degree names, and internal research results.

Run `hugo --minify` to build. For a public-content preview use `hugo server`; use `hugo server -D` to include drafts. Open http://localhost:1313/ and check the homepage navigation and Writing links.

Selected Work and Recent Readings are maintained in `content/_index.md`. Add only verified public work and your own reading history. The homepage includes an explicit RSS subscription link at `/index.xml`.

## Profile photo

Store website-ready images in `static/images/`. Hugo copies these to `/images/` in the built site. The homepage photo is `static/images/profile.jpg`; its URL is configured by `profileImage` in `content/_index.md`. Replace that file to update the photo. The original `IMG_5315.JPG` remains in the repository root as a source copy.

The homepage social icons use `params.socialIcons` in `hugo.yaml` and PaperMod's built-in icon partial.
