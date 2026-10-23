THOMDUCK ADMIN + BACKEND PACKAGE

This package is for a Node.js-compatible backend host, not GitHub Pages. Extract it, install Node.js dependencies with `npm install`, configure environment variables using the host's secret/environment settings, then start with `npm start`.

Required environment variables in production:
- NODE_ENV=production
- PORT (provided by host)
- JSONBIN_BIN_ID (a dedicated, clean Thomduck bin)
- JSONBIN_ACCESS_KEY (valid server-side API key)
- SESSION_SECRET (random secret of at least 32 characters)
- ADMIN_USERNAME=LordTG
- ADMIN_PASSWORD_HASH (bcrypt hash for the requested admin password; do not store the plain password in source control)

The sample .env.example contains placeholders only. Do not commit a real .env or API key. The supplied JSONBin credential has not been verified; confirm it is a valid API key before deployment. Do not migrate old customer records into the Thomduck bin.

The admin page expects to call /api endpoints on the same origin as this backend. If frontend is hosted separately on GitHub Pages, configure a secure API base URL and CORS/session cookies appropriately before expecting admin and customer actions to work. This package is not proof of live JSONBin connectivity.
