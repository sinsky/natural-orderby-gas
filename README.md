# export-gas-library

Support tool to export Node.js libraries to GAS

## Convert Node.js library

### first setup

```shell
git clone https://github.com/sinsky/export-gas-library.git
cd export-gas-library
yarn install
```

### Install the library you want to convert

```shell
yarn add <library>
```

### edit `src/index.js`

```javascript
// Choose the function to call depending on the library
global.Library = require("<library>");
```

### script build

```shell
yarn run build
```

`dist/index.js` to see

### Push to GoogleAppsScript

```shell
yarn clasp login --status
# ok
# You are logged in as your.email@example.com

yarn clasp create --title <Your GAS Project name> --type standalone --rootDir ./dist
mv ./dist/.clasp.json ./
yarn run clasp push
```

## Example

Fuse.js is install.

```shell
yarn add fuse.js
```

Edit `src/index.js`

```javascript
global.Fuse = require('fuse.js/dist/fuse');
```

build scripts

```shell
yarn run build
```

push GoogleAppsScript

```shell
yarn run clasp push
```

Spread the word about your built scripts!

1. `.clasp.json` -> scriptId
2. Script ID will be provided.
