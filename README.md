# prettier-config

> Reusable Prettier config with a parallel Oxfmt export for migrations.

## Install

```sh
pnpm add --save-dev --save-exact @shelf/prettier-config
```

## Legacy Prettier Usage

Keep using the package root while a repo still formats through Prettier:

```json
{
  "prettier": "@shelf/prettier-config"
}
```

The legacy Prettier config stays published at the package root for non-migrated repos.

## Oxfmt Usage

For migrated repos, add a local `oxfmt.config.ts` and import the shared config from `@shelf/prettier-config/oxfmt`:

```ts
import baseConfig, {
  recommendedIgnorePatterns,
} from '@shelf/prettier-config/oxfmt';

export default {
  ...baseConfig,
  ignorePatterns: [...recommendedIgnorePatterns],
};
```

## Shared Oxfmt Config

```js
{
  printWidth: 100,
  singleQuote: true,
  bracketSpacing: false,
  trailingComma: 'es5',
  arrowParens: 'avoid',
  sortPackageJson: false,
}
```

`recommendedIgnorePatterns` starts intentionally small:

```js
['coverage/**']
```

Repo-specific ignore rules should stay local in each repo's `oxfmt.config.ts`.

## Migration Guide

The staged Oxfmt migration guide/prompt/skill lives in the context repository under `docs/oxfmt-migration.md`.

## Publish

```sh
pnpx np
```

## License

MIT © [Shelf](https://shelf.io)
