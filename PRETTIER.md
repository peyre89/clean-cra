# How was Prettier set up?

<br />

The dependencies

```
yarn add --dev husky lint-staged prettier
```

<br />

New file `lint-staged.config.js`

```js
module.exports = {
  "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}": [
    "prettier --write"
  ]
}
```

<br />

New file `prettier.config.js`

```js
module.exports = {
  "singleQuote": true,
  "quoteProps": "consistent",
  "arrowParens": "avoid"
}
```

<br />

New file `.prettierignore`

```
node_modules/
public/
build/
```

<br />

And finally

```sh
npx husky install
npx husky add .husky/pre-commit "yarn lint-staged"
```
