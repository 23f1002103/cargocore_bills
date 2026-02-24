# Salary Slip Document Generation (CargoCore Docs Demo)

Static Vue 3 + Vite demo showcasing 10 logistics documents (login/signup lives in another branch). Each document is a self-contained component with its own mock data defaults.

## Quick start
- Install: `npm install`
- Run dev server: `npm run dev` then open the shown localhost URL.
- Build: `npm run build`

## Project structure
- `src/app/App.vue` – renders all documents.
- `src/app/components/*` – individual documents (Volume Estimate, Quotation, Booking Confirmation, Labor Assignment, Pick List, Asset Checkout, Trip Manifest, POD, Tax Invoice, Vehicle Safety Checklist).
- `src/styles/*` – shared styles.
- `src/assets/*` – logos/seal images used in headers.

## Data
All components use their own `defineProps` defaults, so they render correctly without any props. No API/backend wiring yet.

## Deploy
Netlify ready (see `netlify.toml`). Standard Vite `npm run build` output.
