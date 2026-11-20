# Farm Management Admin Template

A minimal Vue admin shell for building farm management applications. It includes responsive
navigation, breadcrumbs, theme switching, account-menu scaffolding, and a blank dashboard.

## Technology

- Vue 3 and Vue Router
- Pinia
- Reusable Vue component and icon libraries
- Vite and Sass

## Requirements

Use Node.js `^20.19.0` or `>=22.12.0` with npm.

## Commands

```bash
npm ci
npm run dev
npm run lint
npm run build
npm run preview
```

The development server runs at `http://localhost:3000`.

## Structure

- `src/components` contains the reusable application chrome.
- `src/layouts` contains the default admin layout.
- `src/router` defines the Dashboard route and fallback redirect.
- `src/stores` contains sidebar and theme state.
- `src/views/dashboard` is the blank starting page for application features.


## License

Copyright (c) 2026 Bagus Pribadi. This project is open source and available under the [MIT License](LICENSE).