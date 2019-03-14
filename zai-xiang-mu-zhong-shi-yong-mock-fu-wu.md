# 在项目中使用

**1、针对PHP的接口做处理**

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

上述的这种操作方法很简单，在mock环境的

**2、针对Pb的接口做处理**

