# eslint-config-airbnb

[![npm version](https://badge.fury.io/js/eslint-config-airbnb.svg)](http://badge.fury.io/js/eslint-config-airbnb)

This package provides Airbnb's .eslintrc as an extensible shared config.

## Usage

We export three ESLint configurations for your usage.

### eslint-config-airbnb

Our default export contains most of our ESLint rules, including ECMAScript 6+ and React. It requires `eslint`, `eslint-plugin-import`, `eslint-plugin-react`, `eslint-plugin-react-hooks`, and `eslint-plugin-jsx-a11y`. Note that it does not enable our React Hooks rules. To enable those, see the [`eslint-config-airbnb/hooks` section](#eslint-config-airbnbhooks).

If you don't need React, see [eslint-config-airbnb-base](https://npmjs.com/eslint-config-airbnb-base).

1. Install the correct versions of each package, which are listed by the command:

  ```sh
  npm info "eslint-config-airbnb@latest" peerDependencies
  ```

  If using **npm 5+**, use this shortcut

  ```sh
  npx install-peerdeps --dev eslint-config-airbnb
  ```

  If using **yarn**, you can also use the shortcut described above if you have npm 5+ installed on your machine, as the command will detect that you are using yarn and will act accordingly.
  Otherwise, run `npm info "eslint-config-airbnb@latest" peerDependencies` to list the peer dependencies and versions, then run `yarn add --dev <dependency>@<version>` for each listed peer dependency.

  If using **npm < 5**, Linux/OSX users can run

  ```sh
  (
    export PKG=eslint-config-airbnb;
    npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG@latest"
  )
  ```

  Which produces and runs a command like:

  ```sh
  npm install --save-dev eslint-config-airbnb eslint@^#.#.# eslint-plugin-jsx-a11y@^#.#.# eslint-plugin-import@^#.#.# eslint-plugin-react@^#.#.# eslint-plugin-react-hooks@^#.#.#
  ```

  If using **npm < 5**, Windows users can either install all the peer dependencies manually, or use the [install-peerdeps](https://github.com/nathanhleung/install-peerdeps) cli tool.

  ```sh
  npm install -g install-peerdeps
  install-peerdeps --dev eslint-config-airbnb
  ```
  The cli will produce and run a command like:

  ```sh
  npm install --save-dev eslint-config-airbnb eslint@^#.#.# eslint-plugin-jsx-a11y@^#.#.# eslint-plugin-import@^#.#.# eslint-plugin-react@^#.#.# eslint-plugin-react-hooks@^#.#.#
  ```

2. Add `"extends": "airbnb"` to your `.eslintrc`

### eslint-config-airbnb/hooks

This entry point enables the linting rules for React hooks (requires v16.8+). To use, add `"extends": ["airbnb", "airbnb/hooks"]` to your `.eslintrc`.

### eslint-config-airbnb/whitespace

This entry point only errors on whitespace rules and sets all other rules to warnings. View the list of whitespace rules [here](https://github.com/airbnb/javascript/blob/master/packages/eslint-config-airbnb/whitespace.js).

### eslint-config-airbnb/base

This entry point is deprecated. See [eslint-config-airbnb-base](https://npmjs.com/eslint-config-airbnb-base).

### eslint-config-airbnb/legacy

This entry point is deprecated. See [eslint-config-airbnb-base](https://npmjs.com/eslint-config-airbnb-base).

See [Airbnb's JavaScript styleguide](https://github.com/airbnb/javascript) and
the [ESlint config docs](https://eslint.org/docs/user-guide/configuring#extending-configuration-files)
for more information.

## Improving this config

Consider adding test cases if you're making complicated rules changes, like anything involving regexes. Perhaps in a distant future, we could use literate programming to structure our README as test cases for our .eslintrc?

You can run tests with `npm test`.

You can make sure this module lints with itself using `npm run lint`.
