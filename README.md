# aboutblank.me

A small blog about the challenges of a simple engineers life.

[**aboutblank.me**](https://aboutblank.me)


## 🚀 Getting started

1. **Important:** Ensure that [pnpm](https://pnpm.io/installation) is installed
1. Clone the [aboutblank.me](https://github.com/thoomi/aboutblank.me.git) repository.
1. Install dependencies.
   ```shell
   pnpm install
   ```
1. Run the development server.
   ```shell
   pnpm dev
   ```

## 📝 How to

### Add content

This theme features a CLI to help you scaffold new blog posts. It asks you questions to fill out the frontmatter and creates a file in the end. Run the CLI:

```shell
pnpm assistant
```

If you want to extend it, change the [`assistant.ts`](./scripts/assistant.ts) file.

### Change constants

Parts of the theme are referencing [`constants.ts`](./src/constants.ts) to e.g. set the site title or main navigation. Modify its contents to suit your site before deploying it.

### Change existing tags / Add new tags

Inside [`constants.ts`](./src/constants.ts) the `FRONTMATTER_TAGS` map contains the available tags for your site. You need to add your display name and slug of the tag inside this map. The display name will be used in the UI and the slug will be used in the URL.

It's referenced by Astro's content collections and also by the [`assistant.ts`](./scripts/assistant.ts) file.

You can add a new tag like so:

```ts
export const FRONTMATTER_TAGS = new Map(
	[
		// Existing tags...
		['Display name', 'slug-of-your-tag'] as const,
	],
)
```

## 🔍 Reference

### Blog post frontmatter

By default, these frontmatter fields are available. You need to change [`content.config.ts`](./src/content.config.ts) to adjust it.

```yaml
title: Markdown Reference Overview
slug: markdown-reference-overview
description: A post showcasing the markdown formatting of a post
date: 2025-02-18
lastUpdated: 2025-02-18
tags:
  - General
  - MDX
searchIndex: true
image: https://absolute-link.google.com/image.png
```