# VSCode+Prettier+Eslint

## Prettier extension

1.  install `Prettier - Code formatter` Prettier extension, then vscode format document will be replaced by Prettier.
2.  User settings

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

1.  `npm install --save-dev eslint`
2.  `$ npm install --save-dev prettier` or `npm install --global prettier`
3.  `$ npm i --save-dev eslint-plugin-prettier eslint-config-prettier`
4.  `.eslintrc`
    ```json
    {
      "extends": ["plugin:prettier/recommended"]
    }
    ```
5.  `package.json`
    ```json
    "scripts": {
        "format": "./node_modules/.bin/prettier --write 'webapp/**/*.{js,css,json.less}'",
        "lint-js": "./node_modules/.bin/eslint 'webapp/**/*.js'",
        "format-js": "./node_modules/.bin/eslint --fix 'webapp/**/*.js'",
        "eslint-check": "./node_modules/.bin/eslint --print-config .eslintrc | eslint-config-prettier-check"
    },
    ```
6.  `.eslintrc`

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

_Above solve single file format. But how about multi-files._

## Questions

1.  设置了保存的时候格式化，Prettier 支持的格式都会被自动格式化，按照设置。我们设置用`"eslint.autoFixOnSave": true,` 和`"editor.formatOnSave": false`，解决了按照 eslint 中的设置格式化代码在每次保存的时候，而不是 VSCode 设置。但是如果要批量处理呢？批量处理所有文件呢？

> 批量处理可以调用`eslint --fix glob` for JS base on eslint rule settings incloude prettier settings，js 格式化就用此命令
> 如果是其他 prettier 支持的文件如 json，less，css，md…，用 eslint 就不能处理了。

## Reference

- [configure-prettier-and-eslint-in-visual-studio-code/](https://www.39digits.com/configure-prettier-and-eslint-in-visual-studio-code/)
