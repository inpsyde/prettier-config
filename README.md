# Inpsyde Prettier Config

This package provides the shared [Prettier](https://prettier.io/) configuration we use across teams and projects at Inpsyde.

## Installation

```text
npm install --save-dev --save-exact prettier @inpsyde/prettier-config
```

To install this package, create a `.npmrc` file in the project root (the same directory as your package.json file) with the following details:

```text
@inpsyde:registry=https://npm.pkg.github.com/
```

This is to make that packages from the owner `@inpsyde` are downloaded from GitHub's registry. If this is entirely new to you, check the [Installing a package](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#installing-a-package) section in the official docs.

## Usage

To use the shared configuration, add the following line to `package.json`:

```json
{
    "prettier": "@inpsyde/prettier-config"
}
```

And run this command from the command line:

```text
npx prettier ./resources/**/*.{js,ts,tsx} --write
```

You have to specify the correct path for the files you want to format based on your project! This is merely an example.

Check the [CLI](https://prettier.io/docs/en/cli.html) page in the official docs for more details about the command options and flags.

### Add your own rules

If you want to tweak the base configuration, then instead of defining the configuration in the `package.json`, create the `.prettierrc.js` file and add the following:

```js
module.exports = {
    ...require('@inpsyde/prettier-config'),
    semi: false, // or any other option
}
```
You can find more details about the [list of formatting options](https://prettier.io/docs/en/options.html) and the [configuration file](https://prettier.io/docs/en/configuration.html) in the official docs.

### Create a command

Instead of rerunning the `prettier` command from the command line, create a script in the `package.json`:

```json
{
    "scripts": {
        "prettier": "npx prettier ./resources/**/*.{js,ts,tsx} --write"
    }
}
```

## Crafted by Inpsyde

The team at [Inpsyde](https://inpsyde.com) is engineering the Web since 2006.

## License

Copyright (c) Inpsyde GmbH

This software is released under the [MIT](LICENSE) license.
