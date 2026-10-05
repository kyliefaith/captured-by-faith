# Captured by Faith

A static photography portfolio built with Astro and Markdown content collections.

## Local development

Use Node.js 22.12 or newer.

```sh
npm install
npm run dev
```

Astro prints the local preview address in the terminal. The production build is created with:

```sh
npm run check
npm run format:check
npm run build
```

## Edit portfolio stories

Portfolio entries live in `src/content/portfolio`. Copy an existing `.md` file, give it a short filename, and edit its frontmatter:

- `title`: Story title.
- `description`: Short summary used on listing pages and in search metadata.
- `date`: Date in `YYYY-MM-DD` format.
- `category`: A simple label such as `Portraits` or `Families`.
- `cover`: Image path beginning with `/images/`.
- `coverAlt`: A useful description of the image.
- `featured`: Set to `true` to show the entry on the home page.
- `order`: Lower numbers appear first.

Write the story below the second `---` line using standard Markdown.

Journal posts follow the same pattern in `src/content/journal`. Choose one of the supported categories:

- `Bible Study`
- `Life Lately`
- `Goals & Wins`

Set `featured: true` when the post should be considered for the home page.

## Replace sample images

The files in `public/images` are clearly labeled abstract samples. Replace them with optimized `.webp`, `.avif`, `.jpg`, or `.png` files and update the matching `cover` and `coverAlt` values in Markdown.

For best results:

- Use images at least 1600 pixels wide.
- Keep individual files reasonably small for fast loading.
- Preserve the width and height attributes in components to prevent layout shift.
- Replace `public/images/og-captured-by-faith.svg` with a 1200 by 630 pixel social image when final photography is available, then update the default image path in `src/layouts/BaseLayout.astro`.

## Site details

Global colors, spacing, type, focus styles, responsive behavior, dark mode, and reduced-motion behavior are in `src/styles/global.css`.

The public URL is configured in `astro.config.mjs`:

- Site: `https://kyliefaith.github.io`
- Base path: `/captured-by-faith`

Use `withBase()` from `src/utils/paths.ts` for internal links and public asset paths.

## Deployment

`.github/workflows/deploy.yml` builds and deploys the site after every push to `main` using the official Astro and GitHub Pages actions.

In the repository settings, open **Pages** and set **Source** to **GitHub Actions** once. After the workflow completes, the site is available at:

`https://kyliefaith.github.io/captured-by-faith/`
