# mostafapalizdar.dev

Personal blog and portfolio site for Mostafa Palizdar — Senior C#/.NET developer based in Munich.

Built with [Astro](https://astro.build). Deployed on Vercel.

**Live:** [mostafapalizdar.dev](https://mostafapalizdar.dev)

## Stack

- Astro 5 with MDX and Sitemap
- Markdown content collections
- Deployed via Vercel (auto-deploy on push to main)

## Local development

```sh
npm install
npm run dev
```

## Adding a post

Create a `.md` file in `src/content/blog/` with this frontmatter:

```markdown
---
title: "Post title"
description: "Short description"
pubDate: 2026-04-03
---
```

## Commands

| Command           | Action                              |
| :---------------- | :---------------------------------- |
| `npm run dev`     | Start local dev server at :4321     |
| `npm run build`   | Build to `./dist/`                  |
| `npm run preview` | Preview build locally               |
