# prettier-config

> Reusable prettier config

## Install

```
$ yarn add --dev @shelf/prettier-config
```

## Usage

In your `package.json`

```json
{
  "prettier": "@shelf/prettier-config"
}
```

## Config Content

```js
module.exports = {
  printWidth: 100,
  singleQuote: true,
  bracketSpacing: false,
  trailingComma: 'es5',
  parser: 'typescript',
  arrowParens: 'avoid'
};
```

## Publish

```sh
$ git checkout master
$ yarn version
$ yarn publish
$ git push origin master --tags
```

## License

MIT © [Shelf](https://shelf.io)
