```React.render```是```React.js```里最为基础也是最为重要的一个函数之一。

对一个```DOM 节点```多次使用该函数，最终会获得怎样的结果呢?

以下代码：
1. 首先使用```createClass```方法建立了一个简单的```Hello```类；
2. 然后在```JSX```中两次实例化该类；
3. 最后在```DOM 节点``` ```content```中两次使用```React.render```方法。

``` javascript
//Build Class
var Hello = React.createClass({
    render: function () {
		return (
			<div>Hello, {this.props.name}</div>
        );
    }
});

//Instanciate
var divElement1 = <Hello name="Spencer" />;
var divElement2 = <Hello name="Emily" />;

//react.render
React.render(divElement1,
	document.getElementById('content'));
React.render(divElement2,
	document.getElementById('content'));
```

最终，在```html```页输出的结果：

```html
Hello, Emily
```

可见，第二次使用```React.render()```方法**完全**覆盖了第一次的内容。

> Written with [StackEdit](https://stackedit.io/).