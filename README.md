# Rotary Club Bitola Hugo Website Structure Guide

This document serves as a comprehensive guide to the structure and contents of the Hugo-based Rotary Club Bitola website. Use this as a reference for future maintenance and development.

## Project Overview

The website is built using the Hugo static site generator with a custom theme. It features multilingual support (Macedonian and English), responsive design, and sections for Projects, Members, About, and Contact.

## Directory Structure

```
rotary-club-bitola/
├── archetypes/              # Content templates for new pages
│   ├── default.md           # Default content template
│   ├── members.md           # Template for new member profiles
│   └── projects.md          # Template for new project pages
├── assets/                  # CSS, JS, and other assets for processing
│   ├── css/                 # Stylesheet files
│   │   └── main.css         # Main site stylesheet
│   ├── js/                  # JavaScript files
│   │   └── main.js          # Main site JavaScript
│   └── images/              # Images that need processing
│       └── rotary-wheel.svg # SVG version of Rotary wheel logo
├── hugo.toml                # Main configuration file with multilingual settings
├── README.md                # This file: Rotary Club Bitola Hugo Website Structure Guide
├── content/                 # Markdown content
│   ├── en/                  # English content
│   │   ├── _index.md        # English homepage
│   │   ├── about/           # About section English
│   │   │   └── _index.md    # About main page English
│   │   ├── contact/         # Contact section English
│   │   │   └── _index.md    # Contact page English
│   │   ├── members/         # Members section English
│   │   │   ├── _index.md    # Members listing page English
│   │   │   └── *.md         # Individual member pages English
│   │   └── projects/        # Projects section English
│   │       ├── _index.md    # Projects listing page English
│   │       └── *.md         # Individual project pages English
│   └── mk/                  # Macedonian content (same structure as English)
│       ├── _index.md        # Macedonian homepage
│       ├── about/           # About section Macedonian
│       │   └── _index.md    # About main page Macedonian
│       ├── contact/         # Contact section Macedonian
│       │   └── _index.md    # Contact page Macedonian
│       ├── members/         # Members section Macedonian
│       │   ├── _index.md    # Members listing page Macedonian
│       │   └── *.md         # Individual member pages Macedonian
│       └── projects/        # Projects section Macedonian
│           ├── _index.md    # Projects listing page Macedonian
│           └── *.md         # Individual project pages Macedonian
├── data/                    # JSON/YAML data files
│   └── social.json          # Social media links
├── i18n/                    # Translation files
│   ├── en.yaml              # English translations
│   └── mk.yaml              # Macedonian translations
├── layouts/                 # Templates
│   ├── _default/            # Default templates
│   │   ├── baseof.html      # Base template for all pages
│   │   ├── list.html        # Default list template
│   │   └── single.html      # Default single page template
│   ├── index.html           # Homepage template
│   ├── partials/            # Reusable template parts
│   │   ├── footer.html      # Site footer
│   │   ├── head.html        # Document head with meta tags
│   │   └── header.html      # Site header with navigation
│   ├── projects/            # Project-specific templates
│   │   ├── list.html        # Project listing template
│   │   └── single.html      # Project detail template
│   └── members/             # Member-specific templates
│       ├── list.html        # Member listing template
│       └── single.html      # Member profile template
├── static/                  # Static files (served as-is)
│   ├── images/              # Image files
│   │   ├── rotary-wheel.svg # Rotary wheel SVG logo
│   │   ├── members/         # Member profile photos
│   │   │   └── group-photo.jpg # Group photo for members page
│   │   └── projects/        # Project images
│   ├── favicon.ico          # Site favicon
│   └── robots.txt           # SEO robots instructions
└── README.md                # Project documentation
```

## Key File Descriptions

### Configuration

- **hugo.toml**: Main configuration file that defines site parameters, menu structure, and multilingual settings

### Content Structure

- **content/en/_index.md**: English homepage content with title and description
- **content/mk/_index.md**: Macedonian homepage content with title and description
- **content/*/members/_index.md**: Introduction page for the members section
- **content/*/projects/_index.md**: Introduction page for the projects section
- **content/*/about/_index.md**: Information about the Rotary club
- **content/*/contact/_index.md**: Contact information and meeting details

### Templates

- **layouts/_default/baseof.html**: Base template that defines the overall HTML structure
- **layouts/index.html**: Homepage template with hero section and large Rotary wheel
- **layouts/partials/header.html**: Navigation menu and logo
- **layouts/partials/footer.html**: Footer with social links and meeting information
- **layouts/members/list.html**: Template for displaying the grid of members with intro section
- **layouts/members/single.html**: Template for individual member profiles
- **layouts/projects/list.html**: Template for listing all projects
- **layouts/projects/single.html**: Template for detailed project pages

### Styles

- **assets/css/main.css**: Main stylesheet with responsive design for all pages

### Multilingual Support

- **i18n/en.yaml**: English translations for UI elements
- **i18n/mk.yaml**: Macedonian translations for UI elements

## Content Management

### Member Pages

Each member page (.md file) in content/*/members/ should have front matter:

```yaml
---
title: "Member Name"
date: 2023-03-20T12:00:00+01:00
draft: false
photo: "/images/members/member-name.jpg"
position: "Position Title"
linkedin: "https://linkedin.com/in/member-name"
---

Member biography and information...
```

### Project Pages

Each project page (.md file) in content/*/projects/ should have front matter:

```yaml
---
title: "Project Name"
date: 2023-03-20T12:00:00+01:00
draft: false
image: "/images/projects/project-name.jpg"
summary: "Brief project description"
---

Detailed project information...
```

## Build and Deployment

To build the site:
1. Navigate to the project directory
2. Run `hugo --minify` to generate optimized HTML
3. The built site will be in the `public/` directory
4. Upload the contents of `public/` to your web server

For local development, run `hugo server -D` to start a development server with draft content.

---

This guide serves as a reference for maintaining and extending the Rotary Club Bitola website. Refer to it when adding new content or making structural changes to the site.