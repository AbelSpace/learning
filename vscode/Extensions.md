# VS Code Extensions

> Shell command 'code' successfully installed in PATH.

## Color Theme

- [One Dark Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme).
- [Hop Light](https://github.com/bubersson/hop-theme-vscode)

## File Icon Theme

- [vscode-icons](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons), `ext install "vscode-icons"`

## Git

- [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
- [Git Project Manager](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script)
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

## Markdown

- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint), `ext install markdownlint`
- [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)

## Formatter

- [Prettier formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode), `ext install prettier-vscode`. For JavaScript, CSS, Less, JSON, Markdown.
- [XML Tools](https://marketplace.visualstudio.com/items?itemName=DotJoshJohnson.xml), `ext install xmlTools`

## JavaScript

- [ESlint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

## JSDoc

- [Document This](https://marketplace.visualstudio.com/items?itemName=joelday.docthis)

## Node.js

- [npm](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script)
- [Npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
- [Version Lens](https://marketplace.visualstudio.com/items?itemName=pflannery.vscode-versionlens)

## Others

- [Path Autocomplete](https://marketplace.visualstudio.com/items?itemName=ionutvmi.path-autocomplete)

## Sync

- [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync), `ext install Shan.code-settings-sync`

## Settings

```json
{
  "git.autofetch": true,
  "workbench.iconTheme": "vscode-icons",
  "workbench.colorTheme": "One Dark Pro",
  "npm.enableScriptExplorer": true,
  "gitlens.historyExplorer.enabled": true,
  "editor.renderWhitespace": "all",
  "editor.renderControlCharacters": true,
  "editor.tabCompletion": true,
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": false
  },
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,
  "html.format.wrapAttributes": "force",
  "xmlTools.splitAttributesOnFormat": true,
  "sync.gist": "",
  "sync.host": "",
  "sync.pathPrefix": "",
  "sync.quietSync": false,
  "sync.askGistName": true,
  "sync.removeExtensions": true,
  "sync.syncExtensions": true,
  "sync.autoDownload": false,
  "sync.autoUpload": false,
  "sync.lastUpload": "",
  "sync.lastDownload": "",
  "sync.forceDownload": false
}
```
