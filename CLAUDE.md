# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Type
This is a Shopify Liquid theme called "Vessel" (version 2.1.4) - a complete e-commerce storefront theme with assets, templates, sections, blocks, and snippets.

## Architecture Overview

### Core Structure
- **assets/**: JavaScript, CSS, and media files for theme functionality
- **blocks/**: Reusable Liquid components (prefixed with `_` for partials)
- **config/**: Theme configuration including settings schema and data
- **layout/**: Base HTML structure templates (`theme.liquid`, `password.liquid`)
- **locales/**: Translation files for internationalization (53 languages supported)
- **sections/**: Major page components and section templates
- **snippets/**: Small reusable Liquid components
- **templates/**: Page-specific templates for different Shopify page types

### Key Patterns
- Partial blocks are prefixed with `_` (e.g., `_cart-summary.liquid`, `_product-card.liquid`)
- Section group files use `.json` format for static configuration (e.g., `header-group.json`)
- Theme uses modular component architecture with heavy use of `{% render %}` tags
- Color schemes and styling variables are managed through centralized theme settings

### Liquid Template Architecture
- Main layout: `layout/theme.liquid` - base HTML structure with head/body
- Component rendering: Uses `{% render 'component-name' %}` pattern extensively
- Sections can contain blocks, which can contain sub-blocks for flexible page building
- Settings are accessed via `settings.*` variables (configured in `config/settings_schema.json`)

### Asset Management
- JavaScript files in `assets/` handle interactive functionality (product forms, quick add, zoom dialogs)
- CSS likely managed through Liquid preprocessing in theme files
- No build process - files are served directly by Shopify

### Shopify-Specific Features
- Metafields configuration in `.shopify/metafields.json` for custom product/shop data
- Theme supports transparent headers, sticky navigation, and responsive design
- Internationalization with 53 language files and RTL support

## Development Notes
- This is a standard Shopify Online Store 2.0 theme with section groups
- No package.json or build tools - development is done directly with Liquid templates
- Theme settings are managed through Shopify admin interface
- Files marked as auto-generated (like section group JSONs) should be edited carefully