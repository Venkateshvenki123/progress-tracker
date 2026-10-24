# Cloud, Linux & Networking Training Dashboard

A single-page tracker for a 22-week learning plan, including weekly study logs, topics, projects, scenarios, setup tasks, quiz results, and local JSON/Excel exports.

## Run locally

Open `index.html` in a modern browser. The app saves tracker data in that browser's `localStorage`; this repository does not contain your tracker records.

The Supabase client and SheetJS are loaded from public CDNs. Initial loading of those libraries and Excel export may require an internet connection.

## Deploy to Render

1. Push this repository to GitHub.
2. In Render, create a **Static Site** connected to the repository and the `main` branch.
3. Leave the build command blank and set the publish directory to `.`.
4. Deploy and open the HTTPS URL provided by Render.

## Optional Supabase sync

Cloud sync requires a Supabase project with compatible `vault_create`, `vault_get`, and `vault_save` RPC functions. That database setup and live sync have **not** been verified for this deployment. Do not rely on cloud sync or device pairing until the database functions, permissions, conflict behavior, and two-device workflow have been tested against your project.

If you configure the app, use only the Supabase project URL and a public anon/publishable key. Never put a service-role or secret key in this static app or repository. The public key does not protect vaults by itself: security depends on correctly restricted database functions and safeguarding each private pairing link. Anyone with a pairing link can access its vault.

## Data and security notes

- Tracker records and cloud configuration are stored in browser `localStorage`.
- JSON backup and Excel export operate on the current browser's local tracker state.
- Do not commit private pairing links, bearer tokens, service-role keys, exported backups, or personal tracker data.
- A public GitHub repository exposes its source code to everyone. Review changes before pushing.
