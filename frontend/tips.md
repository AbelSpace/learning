# Tips for SAPUI5 and JS

## bind issue

```javascript
function abc() {}
function bcd(a, b) {
    console.log(a === b)
}
bcd(abc, abc) //true
bcd(abc.bind(this), abc.bind(this)) //fase
```
