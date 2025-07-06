# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based GitHub Pages documentation site for SASIE (SAS Interface Extension), a customizable overlay application for the SAS Turnout Dashboard. The repository contains:

- **Website**: Jekyll documentation site in the `/docs` directory
- **Assets**: Images, fonts, and stylesheets for the documentation
- **Theme**: Uses the minimal Jekyll theme with customizations

## Development Commands

### Initial Setup
```bash
cd docs
script/bootstrap
```

### Local Development
```bash
cd docs
bundle exec jekyll serve
```
Visit http://localhost:4000 to preview the site locally.

### Build and Test
```bash
cd docs
script/cibuild
```
This runs the full CI pipeline including:
- Jekyll build
- HTML validation with htmlproofer
- Rubocop linting
- Custom HTML validation
- Gem building

### Manual Commands
```bash
# Build the site
bundle exec jekyll build

# Run linting
bundle exec rubocop -D --config .rubocop.yml

# Test HTML
bundle exec htmlproofer ./_site --check-html --check-sri
```

## Architecture

### Directory Structure
- `/docs/` - Jekyll site root
- `/docs/_config.yml` - Site configuration (title: SASIE, theme: jekyll-theme-minimal)
- `/docs/_layouts/` - Custom layout templates
- `/docs/_includes/` - Reusable template components
- `/docs/_sass/` - Sass stylesheets and font definitions
- `/docs/assets/` - Static assets (images, fonts, CSS, JS)
- `/docs/script/` - Build and deployment scripts

### Key Configuration
- Uses jekyll-theme-minimal as base theme
- Custom logo and branding for SASIE
- Google Analytics integration via custom head includes
- Font customization with Noto Sans variants
- Downloads enabled for release binaries

### Content Management
- Main content in `/docs/index.md`
- Jekyll front matter for layout control
- Markdown content with custom styling
- Image assets organized in `/docs/assets/img/`

## Working Directory Context

Always run Jekyll commands from the `/docs` directory, not the repository root. The root README.md is minimal and the actual documentation site lives in the `docs/` subdirectory.