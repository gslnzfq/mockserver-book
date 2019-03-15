# 常见的Mock系统

## 1、RAP

> 开发者：阿里妈妈前端团队

v0.14.16（就不看了，后台java实现，对我们维护不太友好）：

[http://rapapi.org/org/index.do](http://rapapi.org/org/index.do)

v2：

前端架构\(rap2-dolores\)

* React / Redux / Saga / Router
* Mock.js
* SASS / Bootstrap 4 beta
* server: nginx

后端架构\(rap2-delos\)

* Koa
* Sequelize
* MySQL
* Server
* server: node

缺点：

* 社区版本没有管理员，密码忘记了，需要在数据库修改；
* 部署需要MySQL，Redis，Node.js环境，不过可以使用docker部署；

![](/assets/rap2.png)

Link：[http://rap2.taobao.org/](http://rap2.taobao.org/)

Wiki：[https://github.com/thx/rap2-delos/wiki](https://github.com/thx/rap2-delos/wiki)

## 2、Easy Mock

> 开发者：杭州大搜车前端

技术架构：

* Node.js
* MongoDB
* Redis

![](/assets/easy-mock-cap.png)

Link：[https://easy-mock.com/](https://easy-mock.com/)

Repos：[https://github.com/easy-mock/easy-mock.git](https://github.com/easy-mock/easy-mock.git)

Wiki：[https://github.com/easy-mock/easy-mock/blob/dev/README.zh-CN.md](https://github.com/easy-mock/easy-mock/blob/dev/README.zh-CN.md)

