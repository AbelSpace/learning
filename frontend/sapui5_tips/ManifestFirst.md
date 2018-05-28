# Manifest First Function

- [Manifest First Function](https://sapui5.hana.ondemand.com/#/topic/be0cf40f61184b358b5faedaec98b2da)

The component factory function sap.ui.component enables you to load the manifest.json before the component instance is created. With this, you can preload the dependencies (libraries and components) and, thus, improve the performance for loading the component. The preload is also available for models, which can be flagged for preload during component loading.

```javascript
// load via manifest option
sap.ui.component({
  name: "sap.my.component",
  manifest: true
});
```

```json
"sap.platform.runtime": {
  "componentProperties": {
    "manifest": true // new
  },
  "hasValidManifest": false
}
```