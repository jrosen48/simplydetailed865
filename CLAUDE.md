# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Quarto website for Simply Detailed LLC, a locally-owned cleaning service in Knoxville, TN. The website is a static business site built with Quarto and published to GitHub Pages.

## Build and Development Commands

### Rendering the Website

```bash
quarto render
```

This builds the entire website and outputs to the `docs/` directory (configured in `_quarto.yml`).

### Preview During Development

```bash
quarto preview
```

Launches a live preview server with auto-reload when files change.

### Publishing

The site is published to GitHub Pages from the `docs/` directory. After making changes:

```bash
quarto render
git add .
git commit -m "Update website"
git push
```

## Architecture

### Quarto Configuration

- **Project Type**: Website
- **Output Directory**: `docs/` (GitHub Pages serves from this directory)
- **Theme**: Cosmo with custom branding
- **Custom Styles**: `styles.css` contains brand-specific styling with teal (#00b3b3) primary color

### Site Structure

The website consists of several `.qmd` (Quarto Markdown) files that define pages:

- `index.qmd`: Home page with company overview and contact information
- `about.qmd`: About page featuring owner Meredith Dalton and work examples
- `location.qmd`: Service area map (embedded Google Maps iframe)
- `photos.qmd`: Photo gallery of work

### Navigation

Navigation is defined in `_quarto.yml` under `website.navbar`. The navbar includes:
- Home (index.qmd)
- About
- Location

### Styling

Custom CSS in `styles.css` uses:
- Primary teal color (#00b3b3) for links and brand
- Purple-to-teal gradients for visual elements
- Card hover effects for interactive elements
- Responsive design with Bootstrap components

### Assets

- `images/`: Contains business photos and logo
  - `FullLogo_Transparent.png`: Company logo
  - Various `.jpeg` files: Before/after cleaning photos

### Output

- `docs/`: Production build directory (served by GitHub Pages)
- `_site/`: Quarto build cache (gitignored)
- `.quarto/`: Quarto metadata and cache (gitignored)

## Content Editing Guidelines

When editing content:
- Images are referenced using Quarto syntax: `![](images/filename.ext){width="300"}`
- Contact information is on the home page (index.qmd)
- HTML can be embedded using `` ```{=html} `` blocks (see location.qmd for example)
- The site uses embedded resources (`embed-resources: true`) for self-contained pages
