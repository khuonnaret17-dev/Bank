# Cambodia Demo Bank

A responsive browser-based banking prototype for learning and demonstrations. It supports KHR and USD sample balances, demo deposits, demo withdrawals, same-currency simulated transfers, transaction history, and CSV export.

## Important limitations
- **DEMO ONLY — NO REAL MONEY.**
- This first prototype runs locally in the browser and saves demo state in `localStorage`.
- It does **not** use Firebase Authentication or Cloud Firestore yet.
- It is not suitable for real banking, real payments, or storing sensitive personal information.
- The current transfer flow is intentionally limited to the user's own demo balance in the selected currency; it does not send funds to other people.
- USD values are stored as integer cents. KHR values are stored as integer riel. Cross-currency transfers are disabled.

## Run it
1. Unzip this folder.
2. Open `public/index.html` in a modern browser.
3. Try demo deposits, withdrawals, same-currency transfers, filters, and CSV export.
4. Use Settings → Reset demo data to restore sample data.

For local development, you can also serve the `public` folder with any static file server.

## Suggested next steps for the Firebase version
1. Create separate development and staging Firebase projects.
2. Add Firebase Authentication for identity and account sessions.
3. Move all financial mutations into authenticated Cloud Functions.
4. Create a server-controlled ledger in Cloud Firestore.
5. Write default-deny Firestore Security Rules and emulator tests.
6. Add idempotency keys, transaction limits, audit logs, and concurrent-transfer tests.
7. Create the React Native / Expo mobile app using the same documented domain rules.
8. Configure billing alerts and monitor usage before deploying Cloud Functions.

Never put Firebase Admin credentials or secrets in frontend code. Firebase Admin SDK calls bypass Firestore Security Rules, so Cloud Functions must perform their own authentication, authorization, and validation.
