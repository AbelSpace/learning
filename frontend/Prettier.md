# Prettier

- [Prettier](https://prettier.io/docs/en/index.html)

## Use ESLint to run Prettier

- [Integrating with ESLint](https://prettier.io/docs/en/eslint.html)
- Github
  - [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier#special-rules)
  - [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier)

1. `$ npm i eslint-plugin-prettier eslint-config-prettier --save-dev`
1. `.eslintrc`
    ```json
    {
    "extends": ["plugin:prettier/recommended"]
    }
    ```
1. `package.json`
    ```json
    "scripts": {
        "format": "prettier --write '**/*.{js,css,md}'",
        "eslint-check": "eslint --print-config .eslintrc | eslint-config-prettier-check"
    },
    ```

### Recommended Configuration

This plugin works best if you disable all other ESLint rules relating to code formatting, and only enable rules that detect patterns in the AST. (If another active ESLint rule disagrees with `prettier` about how code should be formatted, it will be impossible to avoid lint errors.) You can use [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) to disable all formatting-related ESLint rules.

If your desired formatting does not match the `prettier` output, you should use a different tool such as [prettier-eslint](https://github.com/prettier/prettier-eslint) instead.

To integrate this plugin with `eslint-config-prettier`, you can use the `"recommended"` configuration:

1. In addition to the above installation instructions, install `eslint-config-prettier`:

  ```sh
  npm install --save-dev eslint-config-prettier
  ```

1. Then all you need in your `.eslintrc.json` is:

  ```json
  {
    "extends": [
      "plugin:prettier/recommended"
    ]
  }
  ```

This does three things:

1. Enables `eslint-plugin-prettier`.
2. Sets the `prettier/prettier` rule to `"error"`.
3. Extends the `eslint-config-prettier` configuration.

You can then set Prettier's own options inside a `.prettierrc` file.

### Options

> Note: While it is possible to pass options to Prettier via your ESLint configuration file, it is not recommended because editor extensions such as `prettier-atom` and `prettier-vscode` **will** read [`.prettierrc`](https://prettier.io/docs/en/configuration.html), but **won't** read settings from ESLint, which can lead to an inconsistent experience.

- The first option:
  - Objects are passed directly to Prettier as [options](https://prettier.io/docs/en/options.html). Example:
    
    ```json
    "prettier/prettier": ["error", {"singleQuote": true, "parser": "flow"}]
    ```

  - Or the string `"fb"` may be used to set "Facebook style" defaults:

    ```json
    "prettier/prettier": ["error", "fb"]
    ```

    Equivalent to:

    ```json
    "prettier/prettier": ["error", {
      "singleQuote": true,
      "trailingComma": "all",
      "bracketSpacing": false,
      "jsxBracketSameLine": true,
      "parser": "flow"
    }]
    ```
  NB: This option will merge and override any config set with `.prettierrc` files (for Prettier < 1.7.0, [config files are ignored](https://github.com/prettier/eslint-plugin-prettier/issues/46))

- The second option:

  - A string with a pragma that triggers this rule. By default, this rule applies to all files. However, if you set a pragma (this option), only files with that pragma in the heading docblock will be checked. All pragmas must start with `@`. Example:

    ```json
    "prettier/prettier": ["error", null, "@prettier"]
    ```

    Only files with `@prettier` in the heading docblock will be checked:

    ```js
    /** @prettier */

    console.log(1 + 2 + 3);
    ```

    Or:

    ```js
    /**
     * @prettier
     */

    console.log(4 + 5 + 6);
    ```

    _This option is useful if you're migrating a large codebase and already use pragmas like `@flow`._
  
  - An object with the following options
  
    - `pragma`: Also sets the aforementioned `pragma`: a string with a pragma that triggers this rule. By default, this rule applies to all files. However, if you set a pragma (this option), only files with that pragma in the heading docblock will be checked. All pragmas must start with `@`.
    
      ```json
      "prettier/prettier": ["error", null, {
        "pragma": "@prettier"
      }]
      ```
      
    - `usePrettierrc`: Enables loading of the Prettier configuration file, (default: `true`). May be useful if you are using multiple tools that conflict with each other, or do not wish to mix your ESLint settings with your Prettier configuration.
    
      ```json
      "prettier/prettier": ["error", null, {
        "usePrettierrc": false
      }]
      ```

* The rule is autofixable -- if you run `eslint` with the `--fix` flag, your code will be formatted according to `prettier` style.

---