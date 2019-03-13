# Mock是什么

Mock /mɑːk/ adj. 仿制的，模拟的，虚假的，不诚实的

其实在我们前端领域来讲就是造数据的，我们自己造数据不好吗？

## 为什么要使用Mock

在没有Mock服务的时候我们是怎么造数据的？

1、将数据造在代码里，就像这样：

```js
var respData = {
    errcode: 1,
    data: [
        {name: 'zhangsan', age: 20}
    ]
};
```

在React中我们会将造的数据写在state里面，先不发请求获取数据，后期联调的时候再删除掉。

2、使用请求拦截，搞一个json，去请求：

```js
// json
[
    {name: 'zhangsan', age: 20}
]

// js
$.getJSON('./xxx.json').then(data=>{console.log(data)});
```

这个虽然比上一个优秀了一点，用了请求的方式，但是我们的路径在后面联调的时候需要修改，一个还好，多了想了想也累。

3、

