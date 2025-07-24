# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a modern personal website for Sujith Christopher, built with Astro and hosted on GitHub Pages at https://sujithchristopher.github.io/. The website showcases his academic background, research publications, and professional updates with a clean, responsive design.

## Architecture & Structure

- **Astro Framework**: Modern static site generator with TypeScript support
- **Tailwind CSS**: Utility-first CSS framework for styling
- **Responsive Design**: Mobile-first approach with dark mode support
- **Component-Based**: Reusable Astro components for maintainable code
- **Static Site Generation**: Pre-rendered at build time for optimal performance

### Directory Structure
```
src/
├── components/     # Reusable UI components
│   ├── Header.astro
│   └── Footer.astro
├── layouts/        # Page layouts
│   └── Layout.astro
├── pages/          # Route pages
│   ├── index.astro      # About/Homepage
│   ├── research.astro   # Research & Publications
│   ├── news.astro       # News & Updates
│   ├── blog.astro       # Blog listing page
│   └── blog/           # Individual blog posts
│       └── 1.astro     # GdSerial blog post
└── styles/         # Global styles
    └── global.css
public/             # Static assets
├── Sujith.jpg     # Profile image
└── favicon.svg    # Site favicon
```

## Development Workflow

### Local Development
```bash
npm run dev          # Start development server at http://localhost:4321
npm run build        # Build for production
npm run preview      # Preview production build
```

### Content Updates
- **About Page**: Edit `src/pages/index.astro` for bio, education, and experience
- **Research**: Edit `src/pages/research.astro` for publications and research areas
- **News**: Edit `src/pages/news.astro` for timeline updates and achievements
- **Blog**: Edit `src/pages/blog.astro` for blog listing, create new posts in `src/pages/blog/`
- **Styling**: Modify `src/styles/global.css` or use Tailwind classes

### Component Structure
- **Header**: Navigation with mobile menu and dark mode toggle
- **Footer**: Social links and contact information
- **Layout**: Base template with SEO meta tags and structured data

## Key Features

- **Dark Mode**: Automatic theme detection with manual toggle
- **Responsive Design**: Optimized for mobile, tablet, and desktop
- **SEO Optimized**: Meta tags, Open Graph, and JSON-LD structured data
- **Performance**: Static generation with optimized assets
- **Accessibility**: Semantic HTML and ARIA labels
- **Modern UI**: Gradient backgrounds, animations, and clean typography

## Deployment

### GitHub Pages
The site uses GitHub Actions for automated deployment:
- **Trigger**: Push to main branch
- **Build**: Fresh npm install + npm run build creates static files in `dist/`
- **Deploy**: GitHub Pages serves the built files
- **Workflow**: `.github/workflows/deploy.yml`
- **Note**: Uses fresh npm install (no lock file) to avoid platform-specific dependency issues

### Manual Deployment
```bash
npm run build        # Build the site
# The dist/ folder contains the deployable files
```

## Common Development Tasks

### Adding New Publications
1. Edit `src/pages/research.astro`
2. Add new publication card following existing pattern
3. Include appropriate tags and styling

### Adding News Items
1. Edit `src/pages/news.astro`
2. Add new timeline item with proper date formatting
3. Include media embeds if needed (YouTube, etc.)

### Adding Blog Posts
1. Create new file in `src/pages/blog/` (e.g., `2.astro` for post ID 2)
2. Update the `blogPosts` array in `src/pages/blog.astro` with post metadata
3. Follow the existing structure and styling patterns

### Styling Updates
- Use Tailwind utilities for quick styling
- Extend theme in `tailwind.config.mjs` for custom colors/fonts
- Add global styles in `src/styles/global.css`

### Performance Optimization
- Images are served from `public/` directory
- CSS is automatically optimized by Astro
- Components are pre-rendered for fast loading

## Dependencies

- **astro**: ^4.16.12 - Static site generator
- **@astrojs/tailwind**: ^5.1.2 - Tailwind CSS integration
- **tailwindcss**: ^3.4.16 - CSS framework
- **typescript**: ^5.7.2 - Type checking