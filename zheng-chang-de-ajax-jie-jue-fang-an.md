# 正常的Ajax解决方案

**1、我们先做最简单的一个版本**

```js
import Url from 'c-url';
// 我们一般会定义每个环境对应的api地址，例如下面的代码
const proxyUrl = {
    pro: 'https://proxy.upliveapps.com/index/index',
    stage: '//sg-stage-proxy.upliveapp.com/index/index',
    mock: 'http://rap2api.taobao.org/app/mock/162162'
};
// 在这里我们直接使用参数的方式传递一下mock
// http://www.upliveapps.com?env=mock
const requestPrefix = proxyUrl[Url.query('env') || 'pro'];


// 业务代码
$.getJSON('/example/1552544591913')
    .then(data => {
        console.log(data);
    })
    .catch(err => {
        console.log(err);
    })
```

上述的这种操作方法很简单，在mock环境下直接传入env=mock就可以搞定mock环境的切换了。但是，我如果想一部分使用mock，一部分使用现有的接口怎么做处理呢？

例如获取用户信息是已经存在的，但是获取榜单的数据是后台还没有开发好的。所以我们就开始升级代码

**2、部分接口使用mock数据**







