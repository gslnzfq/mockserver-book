# Mock是什么

Mock `/mɑːk/` adj. 仿制的，模拟的，虚假的，不诚实的

其实在我们前端领域来讲就是造数据的，我们自己造数据不好吗？

## 造数据的发展

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

3、本地搞一个Mock-Server，就像那种简单的，然后使用webpack-dev-server的proxy（跨域是不行的，所以需要proxy）来请求：

```js
// server
const express = require('express');
const app = express();
app.get('/users', (req,resp) => res.json([{name:'zhangsan', age:30}]));

// client
$.getJSON('/users').then(data=> {console.log(data)});
```

只要我们mock-server的路由和代理的路由相同，我们在联调的时候只需要修改一下域名就可以了，这也是Mock-Server的雏形。但是还存在一些问题：

* 我们每次加一个接口，都需要写代码，重启Mock-Server
* 每个人都需要一个Mock-Server
* 无法进行协作和api共享
* 我们使用的就是所有接口每次调用返回的都是一样的

## Mock系统出现

Mock系统的出现就解决了上面的问题，下面会简单说一些常见的Mock系统及其构成。

