# Documentation Repository

This is a **Mintlify starter template** repository. Most files are placeholder examples from Mintlify that should be replaced with your actual documentation.

## 📁 Repository Structure

```
docs/
├── docs.json                    # Configuration (customize this)
├── README.md                    # This file
├── CONTRIBUTING.md              # Contribution guide
├── DOCS_STRUCTURE.md            # Quick reference
│
├── ROOT LEVEL - Your main documentation pages
│   ├── index.mdx                # ⚠️ TEMPLATE - Replace with your homepage
│   ├── quickstart.mdx           # ⚠️ TEMPLATE - Mintlify quickstart example
│   ├── development.mdx          # ⚠️ TEMPLATE - Mintlify dev guide example
│   └── native-host.mdx          # ✅ CUSTOM - Actual project documentation
│
├── essentials/                  # ⚠️ TEMPLATE - Mintlify examples
│   ├── markdown.mdx             # Example: Markdown syntax guide
│   ├── code.mdx                 # Example: Code block guide
│   ├── images.mdx               # Example: Image usage guide
│   ├── settings.mdx             # Example: Settings reference
│   ├── navigation.mdx           # Example: Navigation guide
│   └── reusable-snippets.mdx    # Example: Snippets guide
│
├── api-reference/               # ⚠️ TEMPLATE - API doc examples
│   ├── introduction.mdx         # Example: API intro
│   ├── openapi.json             # Example: OpenAPI spec
│   └── endpoint/                # Example endpoint docs
│       ├── get.mdx              # Example: GET /plants
│       ├── create.mdx           # Example: CREATE
│       ├── delete.mdx           # Example: DELETE
│       └── webhook.mdx          # Example: Webhook
│
├── snippets/                    # Reusable content snippets
│   └── snippet-intro.mdx        # ⚠️ TEMPLATE - Example snippet
│
├── images/                      # Image assets (add your own)
├── logo/                        # Logo files (replace with your brand)
└── favicon.svg                  # Site icon (replace with your brand)
```

## ⚠️ Template vs Custom Content

### Template Files (Replace These)
Most files in this repository are **Mintlify template examples**:
- `index.mdx` - Generic Mintlify welcome page
- `quickstart.mdx` - How to use Mintlify (not your project)
- `development.mdx` - Mintlify CLI usage guide
- `essentials/*` - Examples of Markdown/component usage
- `api-reference/*` - Example API documentation structure
- All files in `api-reference/endpoint/` - Placeholder endpoint docs

### Custom Content (Keep/Modify These)
- `native-host.mdx` - **Real documentation** for MCP-B Native Host setup
- `docs.json` - Configuration (already partially customized)
- `README.md`, `CONTRIBUTING.md`, `DOCS_STRUCTURE.md` - Repository meta docs

## 🎯 What This Repository Is

This is a **Mintlify documentation starter** that shows:
- How to structure Mintlify docs
- Example pages and components
- Sample navigation setup
- Template API documentation

**Currently:** Only `native-host.mdx` contains actual project documentation. Everything else is boilerplate.

## 🚀 Local Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mintlify) to preview the documentation locally:

```bash
npm i -g mintlify
```

Run the development server at the root of your documentation (where docs.json is):

```bash
mintlify dev
```

## 🔧 Customizing This Template

### Step 1: Clean Up Template Files
Decide what to keep:
- **Delete** template files you don't need (`essentials/`, example API docs)
- **Replace** `index.mdx` with your actual homepage
- **Remove or repurpose** `quickstart.mdx` and `development.mdx`
- **Keep** `native-host.mdx` (or any custom docs you've added)

### Step 2: Update docs.json
Edit `docs.json` to reflect your documentation structure:
- Remove references to deleted template files
- Update site name, colors, and branding
- Restructure navigation tabs and groups
- Update logo paths

### Step 3: Add Your Content
1. Create `.mdx` files for your documentation
2. Add them to appropriate directories (or create new ones)
3. Reference them in `docs.json` (without .mdx extension)

### Step 4: Replace Branding
- Update `/logo/light.svg` and `/logo/dark.svg` with your logos
- Replace `favicon.svg` with your icon
- Update colors in `docs.json`

## 📝 Adding New Documentation

### Where to Put Files

| Content Type | Location | Example |
|-------------|----------|---------|
| Main guides | Root (`/`) | `getting-started.mdx` |
| API docs | `/api-reference/` | `api-reference/authentication.mdx` |
| Reference docs | Create new folder | `/guides/installation.mdx` |
| Reusable snippets | `/snippets/` | `snippets/common-warning.mdx` |

### Adding a New Page
1. Create your `.mdx` file in the appropriate directory
2. Add frontmatter with title and description:
   ```mdx
   ---
   title: 'Page Title'
   description: 'Page description'
   ---
   ```
3. Add the file path to `docs.json` navigation (without `.mdx`):
   ```json
   {
     "group": "Your Group",
     "pages": ["path/to/file"]
   }
   ```

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
