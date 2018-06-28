# VSCode 自定义代码块 snippet

## 什么是 snippet

snippet[ˈsnɪpɪt]，或者说「code snippet」，指的是能够帮助输入重复代码模式串，比如循环或条件语句，的模板。通过 snippet ，我们仅仅输入一小段代码就可以生成预定义的模板代码，甚至可以通过内部跳转快速补全模板。

## 如何配置 snippet

操作流程

1.  进入 snippet 设置文件

    这里提供了两种方法：

    - 按「Alt」键切换菜单栏，通过文件 > 首选项 > 用户代码片段，选择进入目的语言的代码段设置文件;
    - 通过快捷键「Ctrl + Shift + P」打开命令窗口（all command window），输入「snippet」，通过候选栏中的选项进入目的语言的代码段设置文件。

1.  填写 snippets

## snippet 由三部分组成：

- prefix：前缀，定义了 snippets 从 IntelliSense 中呼出的关键字;
- body： 主体，即模板的主体内容，其中每个字符串表示一行;
- description：说明，会在 IntelliSense 候选栏中出现。未定义的情况下直接显示对象名，上例中将会显示 Print to console。

```javascript
```

## insert snippet

在 VSCode 的用户设置（「Ctrl+Shit+P」在输入框中写「user settings」后点选）中，检索代码段，然后根据提示修改，设置建议优先显示，并且可以通过「TAB」补全 snippet。或者每次「Ctrl+Shit+P」在输入框中写「insert snippet」

## User settings

```json
"editor.snippetSuggestions": "top",
"editor.tabCompletion": true
```

References:

- [VSCode 自定义代码块 snippet](http://elickzhao.github.io/2017/05/VSCode%20%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BB%A3%E7%A0%81%E5%9D%97%20%20snippet/)
