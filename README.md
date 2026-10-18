# Job Application Autofiller

A Chrome extension and full-stack prototype for extracting resume data and helping fill job applications.

## Components

- `Extension/`: Manifest V3 extension with a popup, background service worker, and content script.
- `Backend/`: Node.js/Express API, MongoDB models, authentication routes, and PDF parsing/upload handling.
- `vite-project/`: React/Vite dashboard and profile/upload pages.

## Local setup

Install Node.js and provide your own local service configuration. Do not reuse any committed credentials or real uploaded resumes.

```bash
cd Backend
npm install
node server.js
```

The backend loads `config/config.env`. Its default server port is 3000, while the extension and some dashboard calls target localhost:3004. Align those URLs and the configured port before testing.

In a separate terminal:

```bash
cd vite-project
npm install
npm run dev
```

For the extension, open Chrome's extensions page, enable Developer mode, choose **Load unpacked**, and select `Extension/`.

## Status

This is a prototype, not a guarantee of compatibility with every job portal. Configure MongoDB, allowed origins, authentication, and any media/email providers used by the routes. The backend's `npm test` is a placeholder that exits with an error, not a passing test suite.

## Deployment

The frontend can be built with `npm run build` inside `vite-project`. A full deployment also needs a persistent backend, database, upload handling, and production API URLs. Review secrets and uploaded files before publishing a demo. No current live deployment is verified here.
