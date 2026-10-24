# Uplyft

A student career platform built as a college project. It includes:

- Firebase email/password and Google login
- Internship tracks with search and filters
- A one-page resume builder with print/PDF output
- A community feed with likes and comments
- A practice room with a quiz and coding task
- An admin dashboard for managing internships and community posts

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Vite.

## Admin access

Open `/admin` while logged in and use:

```
uplyft2026
```

You can change the code by adding `VITE_ADMIN_CODE` to your environment (locally
in `.env`, or in Vercel project settings).

## Deploy to Vercel

1. Push this folder to a GitHub repository.
2. Import the repository in Vercel.
3. Vercel detects Vite automatically. The included `vercel.json` handles
   routing for React Router.
4. Add your Vercel domain to **Firebase Console → Authentication → Settings →
   Authorized domains** so Google login and email login work in production.
5. Deploy.

Optional environment variables:

```
VITE_ADMIN_CODE=your-code
VITE_FIREBASE_API_KEY=...
VITE_FIREBASE_AUTH_DOMAIN=...
VITE_FIREBASE_PROJECT_ID=...
VITE_FIREBASE_STORAGE_BUCKET=...
VITE_FIREBASE_MESSAGING_SENDER_ID=...
VITE_FIREBASE_APP_ID=...
```

The Firebase values in `src/firebase.js` are public web config fallbacks, so the
site works without environment variables. Override them if you use a different
Firebase project.

## Demo content

Internships, community posts and resume drafts are stored in the browser with
`localStorage`. Changes made in the admin dashboard appear immediately on the
site and can be restored with **Restore demo data**. The resume builder saves
each draft automatically and includes a sample resume you can load to see the
structure. There is no backend or shared database in this version, so data does
not sync between devices or browsers.
