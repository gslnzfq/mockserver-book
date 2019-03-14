# 语法规范

参考链接：[https://github.com/nuysoft/Mock/wiki](https://github.com/nuysoft/Mock/wiki)

**数据模板中的每个属性由 3 部分构成：属性名、生成规则、属性值：**

```
// 属性名   name
// 生成规则 rule
// 属性值   value
'name|rule': value
```

使用：

* 属性名 和 生成规则 之间用竖线 \| 分隔。
* 生成规则 是可选的。
* _生成规则_有7种格式：

```
1. 'name|min-max': value
2. 'name|count': value
3. 'name|min-max.dmin-dmax': value
4. 'name|min-max.dcount': value
5. 'name|count.dmin-dmax': value
6. 'name|count.dcount': value
7. 'name|+step': value'name|min-max': value
```

* 生成规则 的 含义 需要依赖 属性值的类型 才能确定。
* 属性值 中可以含有 @占位符。
* 属性值 还指定了最终值的初始值和类型。



