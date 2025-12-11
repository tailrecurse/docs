# Prediction Bot Documentation

This directory contains the Mintlify documentation site for the Prediction Bot project.

## Setup

### Prerequisites

- **Node.js v20.17.0 or higher** (LTS versions preferred)
- **Yarn (REQUIRED)** - Mintlify requires Yarn to be installed globally:
  ```bash
  npm install -g yarn
  ```

### Installation

1. **Install Mintlify CLI globally** (recommended):

   ```bash
   npm i -g mint
   ```

   Alternatively, you can use `npx mint` without global installation (scripts are configured for this).

2. **Install Yarn globally** (if not already installed):

   ```bash
   npm install -g yarn
   ```

3. Install project dependencies (if any):
   ```bash
   npm install
   # or
   yarn install
   ```

**Note:** The scripts use `npx mint` which works without global installation, but Mintlify itself requires Yarn to be globally installed.

## Development

### Local Preview

Run the development server:

```bash
npm run dev
# or
yarn dev
```

The documentation site will be available at `http://localhost:3001` (or the next available port).

**Note:**

- By default, Mintlify uses port 3000, but the script is configured to use port 3001
- If a port is already in use, Mintlify will automatically try the next available port
- You can skip OpenAPI processing during development for better performance: `mint dev --disable-openapi`

### Building

Build the documentation site:

```bash
npm run build
# or
npx mint build
# or (if installed globally)
mint build
```

### Additional CLI Commands

The Mintlify CLI provides several useful commands:

- **Find broken links**: `mint broken-links`
- **Check accessibility**: `mint a11y`
- **Validate OpenAPI spec**: `mint openapi-check <filename>`
- **Rename files**: `mint rename <old-path> <new-path>`
- **Update CLI**: `mint update`

See the [Mintlify CLI Documentation](https://mintlify.com/docs/cli) for more details.

## Deployment

### Mintlify Dashboard Setup

1. Sign up at [mintlify.com](https://mintlify.com)
2. Create a new project
3. Connect your GitHub repository
4. In **Settings > Git Settings > General**:
   - Toggle **Set up as monorepo** on
   - Enter the path: `apps/docs`
   - Do not include a trailing slash

### File Structure

```
apps/docs/
├── docs.json          # Site configuration (navigation, themes, etc.)
├── index.mdx          # Entry page
├── quickstart.mdx     # Quickstart guide
├── development.mdx    # Development guide
├── guides/            # Additional documentation pages
│   └── overview.mdx
├── essentials/       # Essential documentation guides
├── api-reference/    # API documentation
├── ai-tools/         # AI tools integration guides
└── package.json      # Package configuration
```

## Configuration

### docs.json

The `docs.json` file contains:

- Site name and branding
- Navigation structure
- Theme colors
- Footer links
- Topbar configuration

### Adding New Pages

1. Create a new `.mdx` file in the appropriate directory
2. Add frontmatter with `title` and `description`
3. Add the page to the `navigation` array in `docs.json`

Example:

```mdx
---
title: My New Page
description: Description of my new page
---

Content goes here...
```

## Resources

- [Mintlify Documentation](https://mintlify.com/docs)
- [Mintlify Monorepo Guide](https://mintlify.com/docs/monorepo)
- [MDX Guide](https://mintlify.com/docs/mdx)
