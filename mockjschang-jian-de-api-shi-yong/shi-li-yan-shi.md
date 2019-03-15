# 实例演示

> 参考：[http://mockjs.com/examples.html](http://mockjs.com/examples.html)

1、我们常见的后端接口，PHP返回数据

```json
{
    errcode: 0,
    data: {
        userinfo: {
            name: 'zhangsan',
            addr: '北京市海淀区',
            deviceIP: '192.168.1.1',
            desc: '如果世界最终会毁灭，我愿意多睡一会儿',
            birth: '2018-09-09',
            idcard: '12345319971009765X'
        },
        wallet: {
            balance: 100
        }
    }
}
```

可以使用的下面的规则生成

```js
Mock.mock({
  'errcode|0-1': 0,
  data: {
    userinfo: {
      name: '@CNAME',
      addr: '@county(true)',
      deviceIP: '@ip',
      desc: '@csentence',
      birth: '@date',
      idcard: '@id'
    },
    wallet: {
      'balance|1-20000': 1
    }
  }
})
```

2、我只是让大家感受一下mock.js的魅力，剩下的自己研究研究。



