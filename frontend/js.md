# javaScript

## 循环

### for

- The break statement "jumps out" of a loop.
- The continue statement "jumps over" one iteration in the loop.

```javascript
var text="";
for (i = 0; i < 10; i++) {
    if (i === 3) { break; }
    text += "The number is " + i + "<br>";
}
console.log(text);
text = "";
for (i = 0; i < 10; i++) {
    if (i === 3) { continue; }
    text += "The number is " + i + "<br>";
}
console.log(text);
```

### Array.forEach

### Array.every

*every: 碰到return false的时候，循环中止.*

```javascript
var a = [1, 2, 3, 4, 5]
a.every(function(item, index, arry) {
    console.log(item); //返回1,2
    if (item === 2) {
        return false
    } else {
        return true
    }
})
```

### Array.some

*some: 碰到return ture的时候，循环中止.*

```javascript
var a = [1, 2, 3, 4, 5]
a.some(function(item, index, arry) {
    console.log(item); //返回1,2
    if (item === 2) {
        return true
    } else {
        return false
    }
})
```

### _.forEach in Lodash

```html
<!DOCTYPE html>
<html>
<body>

<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.15.0/lodash.min.js"></script>

<script>
_.forEach([1, 2, 3, 4, 5], function (a) {
    if (a < 3) return;       // continue
    console.log(a);
    if (a > 3) return false; // break
    // return undefined;     // continue, undefined is the standard value of ending a function
});
</script>

</body>
</html>
```

### each in jQuery

```javascript
$("#tblId tr").each(function(i, obj) {
  if($(obj).attr('id') =='idBreakHere' ){
    return false; //this is equivalent of 'break' for jQuery loop
  }
}


$("#tblId tr").each(function(i, obj) {
  if($(obj).attr('id') =='idToFind' ){
    return; //this is equivalent of 'continue' for jQuery loop
  }
}
```