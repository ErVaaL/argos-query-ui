# Argos Query UI

Remote microfrontend for querying Argos resource data. Exposes a Module
Federation remote and provides device search, edit, and deletion workflows
along with measurement browsing and filtering.

## Features

- Device list with pagination and filters (building, room, type, active)
- Edit device details and active status
- Delete devices
- Measurements table for a selected device with type/time filters
- Error banners and loading states

## Requirements

- Node.js 22+
- npm or Yarn

## Install

### npm

```bash
npm install
```

### Yarn

```bash
yarn install --frozen-lockfile
```

## Development

### npm

```bash
npm run dev
```

### Yarn

```bash
yarn dev
```

Default dev server: http://127.0.0.1:5174

## Build

### npm

```bash
npm run build
```

### Yarn

```bash
yarn build
```

## Preview

### npm

```bash
npm run preview
```

### Yarn

```bash
yarn preview
```

## Module Federation

This project exposes `./App` as `remoteQuery` in `rsbuild.config.ts` and is
expected to be consumed by the host shell.

## API

The UI calls the Resource service GraphQL endpoint at
`/api/v1/resource/graphql` by default and expects an `Authorization: Bearer`
token when security is enabled. The dev server proxies `/api/v1` to
`http://localhost:80`.

Override with environment variables:
- `ASSET_PREFIX`
