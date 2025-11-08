# Documentation Structure Quick Reference

This is a quick reference guide for understanding where documentation files are located and where to add new content.

## 🗂️ Directory Structure at a Glance

| Directory | Purpose | When to Use |
|-----------|---------|-------------|
| `/` (root) | Main guide pages | Landing page, quickstart, high-level guides |
| `/essentials/` | Core documentation guides | Best practices, formatting guides, how-tos |
| `/api-reference/` | API documentation | API overview, OpenAPI specs |
| `/api-reference/endpoint/` | Individual endpoints | Specific API endpoint examples |
| `/snippets/` | Reusable content | Content used across multiple pages |
| `/images/` | Image assets | Screenshots, diagrams, icons |
| `/logo/` | Brand assets | Light/dark logo variants |

## 📄 File Types

| Extension | Purpose | Example |
|-----------|---------|---------|
| `.mdx` | Documentation pages | `quickstart.mdx`, `introduction.mdx` |
| `.json` | Configuration/Data | `docs.json`, `openapi.json` |
| `.svg` | Vector graphics | `logo/light.svg`, `favicon.svg` |

## 🎯 Quick Decision Tree

**I want to add...**

### A New Getting Started Guide
- **Location**: Root directory (`/`)
- **File**: `your-guide.mdx`
- **Update**: Add to `docs.json` → `navigation.tabs[0].groups[0].pages`
- **Example**: `"your-guide"`

### A New Essential Guide
- **Location**: `/essentials/`
- **File**: `essentials/your-guide.mdx`
- **Update**: Add to `docs.json` → `navigation.tabs[0].groups[1].pages`
- **Example**: `"essentials/your-guide"`

### A New API Endpoint
- **Location**: `/api-reference/endpoint/`
- **File**: `api-reference/endpoint/your-endpoint.mdx`
- **Update**: Add to `docs.json` → `navigation.tabs[1].groups[1].pages`
- **Example**: `"api-reference/endpoint/your-endpoint"`

### A New API Section
- **Location**: `/api-reference/`
- **File**: `api-reference/your-section.mdx`
- **Update**: Add to `docs.json` → `navigation.tabs[1].groups[0].pages`
- **Example**: `"api-reference/your-section"`

### A Reusable Snippet
- **Location**: `/snippets/`
- **File**: `snippets/your-snippet.mdx`
- **Update**: No need to add to `docs.json`
- **Usage**: Reference via `<Snippet file="your-snippet.mdx" />`

### An Image
- **Location**: `/images/`
- **File**: `images/your-image.png`
- **Update**: No need to add to `docs.json`
- **Usage**: Reference via `![Alt text](/images/your-image.png)`

## 🔍 Current Documentation Pages

### Root Pages (Tab: "Guides" → "Get Started")
- `index.mdx` - Homepage
- `quickstart.mdx` - Quickstart guide
- `development.mdx` - Development setup
- `native-host.mdx` - Native host documentation

### Essentials Pages (Tab: "Guides" → "Essentials")
- `essentials/markdown.mdx` - Markdown guide
- `essentials/code.mdx` - Code formatting
- `essentials/images.mdx` - Image usage
- `essentials/settings.mdx` - Settings configuration
- `essentials/navigation.mdx` - Navigation setup
- `essentials/reusable-snippets.mdx` - Snippets guide

### API Reference Pages (Tab: "API Reference" → "API Documentation")
- `api-reference/introduction.mdx` - API overview

### API Endpoint Pages (Tab: "API Reference" → "Endpoint Examples")
- `api-reference/endpoint/get.mdx` - GET examples
- `api-reference/endpoint/create.mdx` - CREATE examples
- `api-reference/endpoint/delete.mdx` - DELETE examples
- `api-reference/endpoint/webhook.mdx` - Webhook examples

## 🔧 docs.json Navigation Mapping

The `docs.json` file maps to the structure like this:

```
docs.json
└── navigation
    └── tabs[]
        ├── [0] "Guides"
        │   ├── groups[0] "Get Started"
        │   │   └── pages[] → Root directory files
        │   └── groups[1] "Essentials"
        │       └── pages[] → /essentials/ directory files
        └── [1] "API Reference"
            ├── groups[0] "API Documentation"
            │   └── pages[] → /api-reference/ files
            └── groups[1] "Endpoint Examples"
                └── pages[] → /api-reference/endpoint/ files
```

## 📋 Adding New Content Checklist

1. **Create the file** in the appropriate directory
2. **Add frontmatter** (title, description)
3. **Write content** using MDX format
4. **Update docs.json** with file path (no .mdx extension)
5. **Test locally** with `mintlify dev`
6. **Commit and push** changes

## 🚀 Quick Commands

```bash
# Preview documentation locally
mintlify dev

# Reinstall dependencies
mintlify install

# Find all documentation files
find . -name "*.mdx" -type f

# Validate docs.json structure
cat docs.json | jq .
```

## 💡 Pro Tips

1. **File paths in docs.json**: Never include the `.mdx` extension
2. **Relative paths**: All paths in `docs.json` are relative to repo root
3. **Testing**: Always test with `mintlify dev` before committing
4. **Naming**: Use lowercase-with-hyphens for file names
5. **Organization**: Group related docs in subdirectories
6. **Snippets**: Use snippets for content repeated across pages
7. **Images**: Store all images in `/images/` for consistency

## 🔗 Related Files

- `README.md` - Repository overview and structure
- `CONTRIBUTING.md` - Detailed contribution guidelines
- `docs.json` - Navigation and configuration
