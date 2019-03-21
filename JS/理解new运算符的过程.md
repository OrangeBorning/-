# 理解new运算符的过程

```js
var objectFactory = function(){
  var obj = new Object(), // 从 Object.prototype 上克隆一个空的对象
  Constructor = [].shift.call( arguments ); // 取得外部传入的构造器，此例是 Person
​
  obj.__proto__ = Constructor.prototype; // 指向正确的原型
  var ret = Constructor.apply( obj, arguments ); return typeof ret === 'object' ? ret : obj; // 确保构造器总是会返回一个对象
};
```
  JavaScript 是通过克隆 Object.prototype 来得到新的对象，但实际上并不是每次都真正地克隆了一个新的对象。从 内存方面的考虑出发，JavaScript 还做了一些额外的处理，具体细节可以参阅周爱民老师编著的《JavaScript 语言 精髓与编程实践》。这里不做深入讨论，我们暂且把创建对象的过程看成完完全全的克隆。