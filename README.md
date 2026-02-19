# Animated Tabs

A minimalist animated tab interface built with SvelteKit, featuring smooth animations powered by Motion. The project showcases a device mockup design with animated tab indicators and keyboard navigation.

## Features

- **Animated Tab Interface**: Smooth tab switching with bounce and spring animations
- **Keyboard Navigation**: Full keyboard support (Arrow keys, Home, End)
- **Device Frame Design**: Rounded rectangular frame with subtle border styling
- **Accessibility**: ARIA roles and proper tab navigation
- **Modern Stack**: Built with SvelteKit 2, TypeScript, and Motion One
- **Responsive Layout**: Centered design that adapts to viewport size

## Tech Stack

- **Framework**: SvelteKit 2 with Svelte 5
- **Language**: TypeScript
- **Animations**: Motion
- **Styling**: Pure CSS with CSS custom properties
- **Build Tool**: Vite
- **Package Manager**: Bun (compatible with npm/pnpm/yarn)

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd pure-css-page

# Install dependencies
bun install
# or
npm install
```

### Development

```bash
# Start the development server
bun run dev
# or
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Building for Production

```bash
# Build the project
bun run build
# or
npm run build

# Preview the production build
bun run preview
# or
npm run preview
```

### Deployment

This project is configured to deploy to GitHub Pages:

```bash
# Deploy to GitHub Pages
bun run deploy
# or
npm run deploy
```

**Note**: Update the `base` path in `svelte.config.js` to match your GitHub repository name.


## Keyboard Shortcuts

- **Arrow Right/Down**: Navigate to next tab
- **Arrow Left/Up**: Navigate to previous tab
- **Home**: Navigate to first tab
- **End**: Navigate to last tab
