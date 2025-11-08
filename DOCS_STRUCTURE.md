# Documentation Structure Quick Reference

⚠️ **Important**: This is a Mintlify starter template. Most files are examples, not real documentation.

## 📋 Current Repository Status

| Category | Status | Notes |
|----------|--------|-------|
| **Real Documentation** | `native-host.mdx` | MCP-B Native Host setup guide |
| **Template Files** | Most other .mdx files | Mintlify examples to replace/remove |
| **Configuration** | `docs.json` | Partially customized |
| **Meta-Docs** | README, CONTRIBUTING | Repository documentation |

## 🗂️ Directory Structure

| Directory | Current Content | What to Do |
|-----------|----------------|------------|
| `/` (root) | Template examples + native-host.mdx | Keep custom docs, replace templates |
| `/essentials/` | Mintlify formatting examples | Replace with real guides or delete |
| `/api-reference/` | Example API docs (plants endpoint) | Replace with real API docs or delete |
| `/api-reference/endpoint/` | Example endpoints | Replace with real endpoints or delete |
| `/snippets/` | Example snippet | Add reusable content here |
| `/images/` | Example images | Add your screenshots/diagrams |
| `/logo/` | Placeholder logos | Replace with your branding |

## 📄 File Types

| Extension | Purpose | Example |
|-----------|---------|---------|
| `.mdx` | Documentation pages | `quickstart.mdx`, `introduction.mdx` |
| `.json` | Configuration/Data | `docs.json`, `openapi.json` |
| `.svg` | Vector graphics | `logo/light.svg`, `favicon.svg` |

## 🎯 Quick Decision Tree

**I want to add real documentation (not templates)...**

### Option 1: Add to Root (Recommended for Main Docs)
Like `native-host.mdx`:
- **Location**: Root directory (`/`)
- **File**: `your-doc.mdx`
- **Update**: Add to `docs.json` → `navigation.tabs[0].groups[0].pages`
- **Example**: `"your-doc"`

### Option 2: Create New Directory
For organized documentation:
- **Location**: Create `/guides/` or similar
- **File**: `guides/your-doc.mdx`
- **Update**: Create new group in `docs.json` or add to existing
- **Example**: `"guides/your-doc"`

### Option 3: Replace Template Files
Repurpose existing directories:
- **Replace** files in `/essentials/` with your guides
- **Replace** files in `/api-reference/` with your API docs
- **Update** `docs.json` to reflect new content

### Adding Reusable Snippets
- **Location**: `/snippets/`
- **File**: `snippets/your-snippet.mdx`
- **Update**: No need to add to `docs.json`
- **Usage**: `<Snippet file="your-snippet.mdx" />`

### Adding Images
- **Location**: `/images/`
- **File**: `images/your-image.png`
- **Update**: No need to add to `docs.json`
- **Usage**: `![Alt text](/images/your-image.png)`

## 🔍 Current Files in Repository

### Root Pages (Tab: "Guides" → "Get Started")
- `index.mdx` - ⚠️ TEMPLATE - Generic Mintlify welcome page
- `quickstart.mdx` - ⚠️ TEMPLATE - How to use Mintlify
- `development.mdx` - ⚠️ TEMPLATE - Mintlify CLI guide
- `native-host.mdx` - ✅ **REAL** - MCP-B Native Host setup

### Essentials (Tab: "Guides" → "Essentials")
All ⚠️ TEMPLATES - Mintlify component examples:
- `essentials/markdown.mdx` - Markdown syntax examples
- `essentials/code.mdx` - Code block examples
- `essentials/images.mdx` - Image usage examples
- `essentials/settings.mdx` - Settings reference examples
- `essentials/navigation.mdx` - Navigation examples
- `essentials/reusable-snippets.mdx` - Snippets examples

### API Reference (Tab: "API Reference" → "API Documentation")
All ⚠️ TEMPLATES:
- `api-reference/introduction.mdx` - Generic API intro

### API Endpoints (Tab: "API Reference" → "Endpoint Examples")
All ⚠️ TEMPLATES - Example "plants" API:
- `api-reference/endpoint/get.mdx` - Example GET /plants
- `api-reference/endpoint/create.mdx` - Example CREATE
- `api-reference/endpoint/delete.mdx` - Example DELETE
- `api-reference/endpoint/webhook.mdx` - Example webhook

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

## 💡 Key Points

1. **This is a template repository** - Most files are Mintlify examples
2. **Only native-host.mdx is real documentation** currently
3. **Template files can be:**
   - Replaced with your content
   - Deleted (and removed from `docs.json`)
   - Kept as examples/reference
4. **File paths in docs.json**: Never include the `.mdx` extension
5. **Testing**: Always test with `mintlify dev` before committing
6. **Organization**: Create your own structure or use existing directories

## 🚀 Next Steps for This Repository

1. **Decide on structure**: Keep templates or replace them?
2. **Update docs.json**: Remove unused template references
3. **Add real content**: Create documentation for your project
4. **Update branding**: Replace logos, colors, site name
5. **Clean up**: Delete unused template files

## 🔗 Related Files

- `README.md` - Repository overview and structure
- `CONTRIBUTING.md` - Detailed contribution guidelines
- `docs.json` - Navigation and configuration
