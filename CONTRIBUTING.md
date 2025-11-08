# Contributing to Documentation

Thank you for contributing to our documentation! This guide will help you understand the documentation structure and how to make changes.

## 📂 Repository Structure Overview

```
docs/
├── docs.json                          # Main configuration file
├── README.md                          # Repository overview
├── CONTRIBUTING.md                    # This file
├── index.mdx                          # Homepage
├── quickstart.mdx                     # Quickstart guide
├── development.mdx                    # Development guide
├── native-host.mdx                    # Native host documentation
│
├── essentials/                        # Essential guides
│   ├── markdown.mdx
│   ├── code.mdx
│   ├── images.mdx
│   ├── settings.mdx
│   ├── navigation.mdx
│   └── reusable-snippets.mdx
│
├── api-reference/                     # API documentation
│   ├── introduction.mdx
│   ├── openapi.json
│   └── endpoint/                      # Endpoint examples
│       ├── get.mdx
│       ├── create.mdx
│       ├── delete.mdx
│       └── webhook.mdx
│
├── snippets/                          # Reusable content
│   └── snippet-intro.mdx
│
├── images/                            # Image assets
├── logo/                              # Logo files
│   ├── light.svg
│   └── dark.svg
└── favicon.svg                        # Site favicon
```

## 🎯 Where to Add Documentation

### Adding a New Guide Page
**Location**: Root directory or create a new subdirectory

1. Create your `.mdx` file (e.g., `my-guide.mdx`)
2. Add content using MDX format
3. Update `docs.json` navigation to include your page

Example:
```json
{
  "group": "Get Started",
  "pages": [
    "index",
    "quickstart",
    "my-guide"  // Add here (no .mdx extension)
  ]
}
```

### Adding API Documentation
**Location**: `/api-reference/endpoint/`

1. Create a new `.mdx` file in `/api-reference/endpoint/`
2. Add endpoint details using Mintlify API components
3. Add to `docs.json` under "Endpoint Examples" group

Example:
```json
{
  "group": "Endpoint Examples",
  "pages": [
    "api-reference/endpoint/get",
    "api-reference/endpoint/my-endpoint"  // Add here
  ]
}
```

### Adding Essential Guides
**Location**: `/essentials/`

1. Create `.mdx` file in `/essentials/` directory
2. Add to "Essentials" group in `docs.json`

### Adding Reusable Snippets
**Location**: `/snippets/`

1. Create `.mdx` file in `/snippets/`
2. Reference in other pages using:
   ```mdx
   <Snippet file="snippet-intro.mdx" />
   ```

## 📝 Documentation Format

All documentation files use the `.mdx` format (Markdown + JSX). This allows you to:
- Use standard Markdown syntax
- Embed React components
- Use Mintlify-specific components

### File Naming Conventions
- Use lowercase with hyphens: `my-new-guide.mdx`
- Be descriptive: `authentication-setup.mdx` not `auth.mdx`
- Group related content in subdirectories

### Required Frontmatter
Each documentation page should include metadata at the top:

```mdx
---
title: "Page Title"
description: "Brief description of the page content"
---

# Your Content Here
```

## 🔧 Configuration Guide

### docs.json Structure

The `docs.json` file controls the entire documentation site. Key sections:

#### Navigation
```json
{
  "navigation": {
    "tabs": [
      {
        "tab": "Tab Name",
        "groups": [
          {
            "group": "Group Name",
            "pages": ["file-path-without-extension"]
          }
        ]
      }
    ]
  }
}
```

#### Important Notes:
- File paths in `pages` array should NOT include `.mdx` extension
- File paths are relative to the repository root
- Paths use forward slashes: `api-reference/endpoint/get`

## ✅ Before Submitting

### Checklist
- [ ] File is in the correct directory
- [ ] File uses `.mdx` extension
- [ ] File path added to `docs.json` (without .mdx extension)
- [ ] Frontmatter includes title and description
- [ ] Local preview works (`mintlify dev`)
- [ ] All links work correctly
- [ ] Images are in `/images/` directory
- [ ] Code examples are properly formatted

### Testing Locally

1. Install Mintlify CLI:
   ```bash
   npm i -g mintlify
   ```

2. Run development server:
   ```bash
   mintlify dev
   ```

3. Open browser to `http://localhost:3000`

4. Verify:
   - Page appears in navigation
   - Content renders correctly
   - Links work
   - Images load

## 🐛 Common Issues

### Page Shows 404
- **Cause**: File path in `docs.json` doesn't match actual file location
- **Fix**: Ensure path in `docs.json` matches file location (without .mdx)

### Page Doesn't Appear in Navigation
- **Cause**: Not added to `docs.json`
- **Fix**: Add file path to appropriate group in `docs.json`

### Images Don't Load
- **Cause**: Incorrect image path
- **Fix**: Use `/images/filename.png` (absolute path from root)

### Mintlify Dev Not Running
- **Cause**: Dependencies issue
- **Fix**: Run `mintlify install`

## 📚 Resources

- [Mintlify Documentation](https://mintlify.com/docs)
- [MDX Documentation](https://mdxjs.com/)
- [Mintlify Components](https://mintlify.com/docs/components)

## 🤝 Questions?

If you have questions about where to add documentation or how to structure content, please open an issue or reach out to the maintainers.
