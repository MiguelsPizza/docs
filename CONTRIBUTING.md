# Contributing to Documentation

Thank you for contributing! This guide will help you understand this repository and how to make changes.

## ⚠️ Important: Template vs Real Content

This is a **Mintlify starter template** repository. Most files are Mintlify examples, not real documentation:

### Template Files (Mintlify Examples)
- `index.mdx` - Generic Mintlify welcome page
- `quickstart.mdx` - How to use Mintlify
- `development.mdx` - Mintlify CLI guide
- `essentials/*` - Markdown/component examples
- `api-reference/*` - Example API structure

### Real Documentation
- `native-host.mdx` - **Actual MCP-B Native Host documentation**
- Repository meta-docs (README, CONTRIBUTING, DOCS_STRUCTURE)

## 📂 Current Repository Structure

```
docs/
├── docs.json                          # Configuration
├── README.md                          # Repository guide
├── CONTRIBUTING.md                    # This file
├── DOCS_STRUCTURE.md                  # Quick reference
│
├── index.mdx                          # ⚠️ TEMPLATE
├── quickstart.mdx                     # ⚠️ TEMPLATE
├── development.mdx                    # ⚠️ TEMPLATE
├── native-host.mdx                    # ✅ REAL DOCS
│
├── essentials/                        # ⚠️ ALL TEMPLATES
│   ├── markdown.mdx
│   ├── code.mdx
│   ├── images.mdx
│   ├── settings.mdx
│   ├── navigation.mdx
│   └── reusable-snippets.mdx
│
├── api-reference/                     # ⚠️ ALL TEMPLATES
│   ├── introduction.mdx
│   ├── openapi.json
│   └── endpoint/
│       ├── get.mdx
│       ├── create.mdx
│       ├── delete.mdx
│       └── webhook.mdx
│
├── snippets/                          # ⚠️ TEMPLATE
│   └── snippet-intro.mdx
│
├── images/                            # Assets
├── logo/                              # Branding
└── favicon.svg
```

## 🎯 Contributing Real Documentation

When adding **real project documentation** (not template examples):

### Option 1: Add to Root (Like native-host.mdx)
For main documentation pages:

1. Create `your-doc.mdx` in the root directory
2. Add frontmatter and content
3. Add to `docs.json` in the appropriate group:
   ```json
   {
     "group": "Get Started",
     "pages": [
       "index",
       "native-host",
       "your-doc"  // Add here (no .mdx extension)
     ]
   }
   ```

### Option 2: Create New Directory Structure
For organized documentation:

1. Create a new folder (e.g., `/guides/`)
2. Add your `.mdx` files there
3. Update `docs.json` with a new group or add to existing:
   ```json
   {
     "group": "Guides",
     "pages": [
       "guides/installation",
       "guides/configuration"
     ]
   }
   ```

### Option 3: Repurpose Template Directories
You can replace template files in existing directories:

- Replace files in `/essentials/` with actual guides
- Replace `/api-reference/` files with real API docs
- Update `docs.json` references accordingly

### Adding Reusable Snippets
For content used across multiple pages:

1. Create `.mdx` file in `/snippets/`
2. Reference using: `<Snippet file="your-snippet.mdx" />`
3. No need to add to `docs.json`

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
