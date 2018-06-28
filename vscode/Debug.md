# Debug

## Launch.json

Debug grunt sample settings:

```json
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Launch Grunt",
      // "program": "${workspaceFolder}\\node_modules\\@sap\\approuter\\approuter.js"
      // "program": "${env:APPDATA}\\npm\\node_modules\\grunt-cli\\bin\\grunt",
      "program":
        "${workspaceRoot}\\node_modules\\grunt\\node_modules\\grunt-cli\\bin\\grunt",
      "args": ["watch"],
      "stopOnEntry": true,
      "cwd": "${workspaceRoot}"
    }
  ]
}
```
