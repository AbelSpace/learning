# VSCode+Prettier+Eslint

## Prettier extension

1. install `Prettier - Code formatter`  Prettier extension, then vscode format document will be replaced by Prettier.
2. User settings

   Testing as below settings:

   ```json
   {
    "editor.formatOnSave": false,
    "[javascript]": {
        "editor.formatOnSave": true
    },
    "prettier.singleQuote": true
   }
   ```

## ESLint Plugin Prettier

See [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) for more.

1. `npm install --save-dev eslint`
2. `$ npm install --save-dev prettier` or `npm install --global prettier`
3. `$ npm i --save-dev eslint-plugin-prettier eslint-config-prettier`
4. `.eslintrc`
    ```json
    {
    "extends": ["plugin:prettier/recommended"]
    }
    ```
5. `package.json`
    ```json
    "scripts": {
        "format": "prettier --write 'webapp/**/*.{js,css}'",
        "eslint": "./node_modules/.bin/eslint 'webapp/**/*.js'",
        "eslint-fix": "./node_modules/.bin/eslint --fix 'webapp/**/*.js'",
        "eslint-check": "./node_modules/.bin/eslint --print-config .eslintrc | eslint-config-prettier-check"
    },
6. `.eslintrc`

    ```json
    {
        "extends": ["ems-ui/src-config", "plugin:prettier/recommended"],
        "rules": {
            "prettier/prettier": [
            "error",
            {
                "singleQuote": true
            }
            ]
        }
    }
    ```

## User Settings

```json
{
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": false
  },
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true
}
```
