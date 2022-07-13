# Chapter 1

JS 由以下三种组成：

- ECMAScript

- BOM

- DOM

# Chapter 2

noscript 标签是当禁用 script 的时候，或者不支持 script 的时候才显示的

script 标签有个属性叫 crossorign 加上之后就可以对请求进行跨域验证，CDN 加上可以接受到远程的报错信息

script 标签的 src 属性默认是跨域的，如果有 src 属性默认就忽略掉行内 script 代码，如果动态生成 script 标签，然后给 script 标签添加 src 属性，默认是 async 加载的。

# Chapter 3

ECMAScript 严格区分大小写（Windows 不严格）

> 记得学习MarkDown语法  可以在MarkDown编辑器输入图形 然后再查看源代码

## 记得在句尾加上分号

- 如果句尾是函数体 然后第二行是模板字符串或小括号包裹的东西 就会被当做参数

- 如果句尾是数组 然后第二行是[0] 就会被当做数组第几位解释

- 难怪之前在机试之类的写过代码

  ```js
    /*数组被第二行解释*/
       let line = readline()//这一行是数组 紧跟下一行的中括号的最后一个数字会被当做第几个解释
    [...line].forEach(v=>handle(v))
  
    /*函数被第二行解释*/
      function foo(){}
      let gcc=foo
      `myParams`.test(/\w/)
  ```

## 标签函数

当你直接使用模板字符串作为函数的调用方式的时候，这个时候函数的入参会包括这个模板字符串会相当于用 ${a}分割,并且连接成一个数组,然后其他的参数分别是你插入在模板字符串里面的变量

```js
eg:function foo(...params){
   console.log(params)
}
let name = "Yukon"
let level = "great"

foo`${name} is doing ${level} job`

//注意如果变量在最前或最后都会有个空字符串被分割出来
//使用场景: 对输入进行转义
```

