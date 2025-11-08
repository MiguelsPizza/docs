# Documentation Repository

This repository contains the documentation built with Mintlify.

## 📁 Documentation Structure

### Root Directory
The root directory contains the main documentation pages and configuration:

- **`docs.json`** - Main configuration file that defines navigation, theme, and structure
- **`index.mdx`** - Homepage/landing page
- **`quickstart.mdx`** - Quick start guide
- **`development.mdx`** - Development guide
- **`native-host.mdx`** - Native host documentation

### Documentation Directories

#### `/essentials/`
Contains essential guides and best practices:
- `markdown.mdx` - Markdown formatting guide
- `code.mdx` - Code blocks and syntax highlighting
- `images.mdx` - Image usage and formatting
- `settings.mdx` - Settings and configuration
- `navigation.mdx` - Navigation structure guide
- `reusable-snippets.mdx` - Reusable content snippets

#### `/api-reference/`
Contains API documentation:
- `introduction.mdx` - API overview and introduction
- `openapi.json` - OpenAPI specification

#### `/api-reference/endpoint/`
Individual API endpoint documentation:
- `get.mdx` - GET endpoint examples
- `create.mdx` - CREATE/POST endpoint examples
- `delete.mdx` - DELETE endpoint examples
- `webhook.mdx` - Webhook endpoint examples

#### `/snippets/`
Reusable content snippets that can be included in multiple pages:
- `snippet-intro.mdx` - Example snippet

#### `/images/`
Image assets used throughout the documentation

#### `/logo/`
Logo files (light and dark variants)

## 🚀 Local Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mintlify) to preview the documentation locally:

```bash
npm i -g mintlify
```

Run the development server at the root of your documentation (where docs.json is):

```bash
mintlify dev
```

## 📝 Adding New Documentation

### Adding a New Guide
1. Create a new `.mdx` file in the root directory or appropriate subdirectory
2. Add the file path to `docs.json` in the relevant navigation section
3. Use the format: `"path/to/file"` (without the .mdx extension)

### Adding a New API Endpoint
1. Create a new `.mdx` file in `/api-reference/endpoint/`
2. Add the file path to the "Endpoint Examples" group in `docs.json`

### Adding a New Section
1. Create a new directory for your section
2. Add your `.mdx` files to the directory
3. Update `docs.json` to include a new group with the files

## 🔧 Configuration

All navigation, theming, and structure configuration is managed in `docs.json`. Key sections:

- **`navigation.tabs`** - Defines the main tabs (Guides, API Reference)
- **`navigation.tabs[].groups`** - Defines groups within each tab
- **`navigation.tabs[].groups[].pages`** - Lists pages in each group
- **`theme`** - Color scheme and branding
- **`logo`** - Path to logo files

## 📤 Publishing Changes

Install the Mintlify Github App to automatically deploy changes. Changes will be deployed to production automatically after pushing to the default branch.

## 🐛 Troubleshooting

- **Mintlify dev isn't running** - Run `mintlify install` to re-install dependencies
- **Page loads as a 404** - Ensure you're running in a folder with `docs.json` and the page is listed in the navigation
- **Page doesn't appear in navigation** - Check that the file path in `docs.json` matches the actual file location (without .mdx extension)
