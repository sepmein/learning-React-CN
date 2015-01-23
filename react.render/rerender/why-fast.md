为什么`React.render`速度很快？
===

### 摘要

`React`使用差异化算法提升重复渲染时的计算速度，使其能达到宣称的高速度。

### 详细

速度是`React`标榜的核心特质，也是`React`宣称自己更适合于大型项目的主要原因。那么，我们首先要搞懂，在浏览器端，什么是快？什么是慢？

对此，`React`给出的逻辑是：在一台计算机的CPU计算能力一定的情况下，为完成同样的工作，在同等时间内CPU**处理的事务越少，处理速度越快。**

所以在此逻辑下，要使得`id='a'`的`span`变成`id='b'`的`span`  ：

```javascript
<span id="a"></span>
<span id="b"></span>
```

在`DOM`中删除整个`span`，然后再插入一个全新的`span`，赋予其`id`属性，这个做法，是**慢**的。

分析两个`span`的不同之处，发现仅在`id`属性上有差异，因此将前一个`span`的`id`由`a`设置为`b`，这个做法，是**快**的。

#### 引用
http://facebook.github.io/react/docs/reconciliation.html
