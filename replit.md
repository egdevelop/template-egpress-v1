# Riven Blog

A modern, SEO-optimized static blog website built with Astro.js and Tailwind CSS, designed for perfect Web Core Vitals scores and CMS-ready architecture.

## Project Overview

This is a professional blog platform featuring:
- Static site generation with Astro.js
- Markdown-based content management
- SEO optimization with meta tags, Open Graph, and JSON-LD structured data
- Perfect Web Core Vitals optimization
- Responsive design with Tailwind CSS
- Search functionality using Fuse.js
- Category filtering and RSS feed support

## Project Structure

```
├── public/                 # Static assets (favicon, og-image)
├── src/
│   ├── components/        # Reusable Astro components
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   ├── BlogCard.astro
│   │   ├── FeaturedPost.astro
│   │   ├── SearchBar.astro
│   │   ├── CategoryFilter.astro
│   │   ├── AuthorCard.astro
│   │   ├── ShareButtons.astro
│   │   └── RelatedPosts.astro
│   ├── content/
│   │   └── blog/          # Markdown blog posts
│   ├── layouts/
│   │   ├── BaseLayout.astro
│   │   └── BlogPostLayout.astro
│   ├── pages/
│   │   ├── index.astro    # Homepage
│   │   ├── blog/          # Blog listing and post pages
│   │   ├── about.astro
│   │   ├── contact.astro
│   │   ├── terms.astro    # Terms of Service
│   │   ├── privacy.astro  # Privacy Policy
│   │   ├── disclaimer.astro # Disclaimer
│   │   └── rss.xml.js     # RSS feed
│   └── styles/
│       └── global.css     # Global styles with Tailwind
├── content.config.ts      # Content collection schema
└── astro.config.mjs       # Astro configuration
```

## Blog Post Schema

Blog posts use frontmatter with the following fields:
- `title`: Post title
- `description`: Short description for SEO
- `pubDate`: Publication date
- `author`: Object with `name` and optional `avatar`
- `category`: One of: design, technology, research, management, customer-success
- `tags`: Array of tag strings
- `featuredImage`: URL to the featured image
- `featured`: Boolean for homepage featuring
- `draft`: Boolean for draft status

## Commands

- `npm run dev` - Start development server on port 5000
- `npm run build` - Build for production
- `npm run preview` - Preview production build

## Tech Stack

- **Framework**: Astro.js 5.x
- **Styling**: Tailwind CSS 4.x
- **Search**: Fuse.js
- **Image Optimization**: Sharp
- **SEO**: @astrojs/sitemap, @astrojs/rss

## Adding New Blog Posts

Create a new `.md` file in `src/content/blog/` with frontmatter:

```markdown
---
title: "Your Post Title"
description: "A brief description"
pubDate: 2024-01-01
author:
  name: "Author Name"
  avatar: "https://example.com/avatar.jpg"
category: technology
tags: ["tag1", "tag2"]
featuredImage: "https://example.com/image.jpg"
featured: false
draft: false
---

Your content here...
```

## CMS Integration

This project is structured for easy CMS integration. To connect a headless CMS:
1. Replace the file-based content loader in `content.config.ts`
2. Configure your CMS SDK/API
3. Update data fetching in page components

Supported CMS options: Contentful, Sanity, Strapi, Prismic

## GitHub Repository

Repository: https://github.com/egdevelop/riven-blog

## Google AdSense Integration

The site includes placeholder ad slots ready for Google AdSense:
- Located in `src/components/AdPlacement.astro`
- 4 layout types: horizontal, vertical, square, in-article
- Placements on homepage, blog listing, and blog post pages
- Replace placeholder content with actual AdSense code when ready

## Centralized Configuration

The site uses a centralized configuration system in `src/config/siteSettings.ts`:

### Configuration Sections
- **designTokens**: Colors, typography, spacing, border radius, shadows
- **siteSettings**: Site name, logo, SEO defaults, social links, contact info, feature flags
- **contentDefaults**: Navigation (header/footer), homepage content, blog settings, categories

### Helper Functions
```typescript
import { getSiteSettings, getNavigation, getSocialLinks, getCategories } from '../config/siteSettings';
```

### Feature Flags
- `enableSearch`: Toggle search functionality
- `enableCategories`: Toggle category filtering
- `enableNewsletter`: Toggle newsletter section
- `enableComments`: Toggle comments (future)
- `enableRss`: Toggle RSS feed

## Recent Changes

- **November 29, 2024**: Created centralized configuration system (siteSettings.ts), updated Header/Footer/homepage to use config
- **November 28, 2024**: Created GitHub repository, added AdSense placeholder component with strategic ad placements
- **November 28, 2024**: Added legal pages (Terms of Service, Privacy Policy, Disclaimer), removed Download Our App button from header, improved image performance with explicit dimensions
