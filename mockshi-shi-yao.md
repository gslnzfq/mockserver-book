# Mock是什么

> Mock `/mɑːk/` adj. 仿制的，模拟的，虚假的，不诚实的

其实在我们前端领域来讲就是造数据的，是我们自己造数据不好吗，干嘛要用啥工具？

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

// React
class App {
    state = {
        name: 'zhangsan',
        age: 20
    };
    render() {
        return (
            <div>
                大家好，我是{this.state.name},今年{this.state.age}岁
            </div>
        )
    }
}
```

在React中我们会将造的数据写在state里面，先不发请求获取数据，后期联调的时候再删除掉，有时候我们联调的时候忘记删除了，**就会导致请求没有回来的时候页面上显示的假数据**，体验不是很好。

2、使用请求拦截，搞一个json，使用ajax去请求：

```js
// json
[
    {name: 'zhangsan', age: 20}
]

// js
$.getJSON('./xxx.json').then(data=>{console.log(data)});
```

这个虽然比上一个优秀了一点，**用了请求的方式**，但是我们的路径在后面联调的时候需要修改，一个还好，如果涉及到接口又比较多，工作量巨大，并且容易漏掉。

3、本地搞一个API-Server，实现简单的API功能，然后使用webpack-dev-server的proxy（跨域是不行的，所以需要proxy）来请求：

```js
// server
const express = require('express');
const app = express();
app.get('/users', (req,resp) => res.json([{name:'zhangsan', age:30}]));

// client
$.getJSON('/users').then(data=> {console.log(data)});
```

> 注意：这里就需要我们懂一些Node.js和Proxy的知识了。

只要我们API-Server的请求路径和请求方式（POST,GET,PUT,DELETE）和实际后端的路由是相同的，我们在联调的时候只需要修改一下域名就可以了，这也是Mock-Server的雏形。但是还存在一些问题：

* 我们每次加一个接口，都需要加路由代码，重启API-Server；
* 每个人都需要在本地一个API-Server，除非搭建在内部服务器上；
* 我们使用的就是所有接口每次调用返回的都是一样的，_数据没有意义；_
* 无法进行协作和api共享；

## Mock系统出现

Mock系统的出现就解决了上面的问题，下面会简单说一些常见的Mock系统及其构成。

