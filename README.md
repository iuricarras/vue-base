# Vue Base Template

A production-ready Vue 3 starter built with Vite, Tailwind CSS, Pinia, Vue Router, and a shadcn-vue style UI setup.

## What this template includes

- Vue 3 + Vite (`type: module`, fast dev server and build)
- Vue Router (configured in `src/router/index.js`)
- Pinia state management (initialized in `src/main.js`)
- Tailwind CSS with CSS variables and dark mode support (`class` strategy)
- Reusable UI primitives in `src/components/ui` (example: `Button`)
- Utility helpers (`cn`, `valueUpdater`) in `src/lib/utils.js`
- Optional Nix development shell (`flake.nix`)

## Tech stack

- **Core**: Vue 3, Vite
- **State**: Pinia
- **Routing**: Vue Router
- **HTTP**: Axios
- **Styling**: Tailwind CSS + PostCSS + Shadcn-vue


## Getting started

### 1) Prerequisites

- Node.js 18+ (recommended: latest LTS)
- npm (or your preferred package manager)

### 2) Install dependencies

```bash
npm install
```

### 3) Start development server

```bash
npm run dev
```

The dev script runs `vite --host`, so it is exposed on your local network.

### 4) Build for production

```bash
npm run build
```

### 5) Preview production build

```bash
npm run preview
```

## Available scripts

- `npm run dev` — start Vite dev server
- `npm run build` — create production build in `dist/`
- `npm run preview` — preview the built app locally

## Project structure

```txt
src/
	main.js              # app bootstrap (Pinia, router)
	App.vue              # root component (renders RouterView)
	router/index.js      # route definitions
	stores/              # Pinia stores
	views/               # route-level pages
	components/          # shared and feature components
		ui/                # reusable UI primitives
	lib/utils.js         # shared helpers (cn, valueUpdater)
	assets/main.css      # Tailwind + design tokens (light/dark)
```

## Path alias

Use `@` to import from `src`.

Example:

```js
import { Button } from '@/components/ui/button'
```

Configured in:

- `vite.config.js` (runtime/bundler alias)
- `jsconfig.json` (editor intellisense)

## Routing

Routes are defined in `src/router/index.js`.

Current default routes:

- `/` → `MainPage`

Add new pages by creating a view/component and registering a route in the router.

## State management (Pinia)

Pinia is registered in `src/main.js`:

```js
app.use(createPinia())
```

Create stores inside `src/stores/`.

## API setup (Axios)

Axios is already installed and initialized in `src/main.js`:

```js
axios.defaults.baseURL = ''
```

Set your API base URL there (or move it to environment variables for multiple environments).

## UI components

This template includes a reusable button component from shadcn-vue.

Use it like:

```vue
<script setup>
import { Button } from '@/components/ui/button'
</script>

<template>
	<Button>Click me</Button>
</template>
```

You can add more components from the shadcn-vue store.

## Optional: Nix shell

If you use Nix, enter the dev shell with:

```bash
nix develop
```

`flake.nix` currently provides `nodejs`.

<!-- ## Next steps after cloning this template

- Rename project in `package.json`
- Set `axios.defaults.baseURL`
- Replace starter routes/components
- Add your own Pinia stores and feature modules -->


