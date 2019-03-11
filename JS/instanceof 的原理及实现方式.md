# instanceof 的原理及实现方式

我不知道该怎么开头合适，JS这个目录就用我今天面试到这个题来吧。

当时被问到第一瞬间我还是有印象的，和 typeof 类似。但是当时回答的不是很明白。

instanceof *运算符* 用来验证，一个*对象*是否为*指定的构造函数的实例*。

```js
var arr = []

arr instanceof Object
// true arr 对象是 Object 的实例
arr instanceof Array
// true arr 对象是 Array 的实例
arr.constructor === Object
// false 
arr.constructor === Array
// true arr 对象的构造函数是 Array
var Obj= {}

Obj instanceof Object
// true Obj 对象是 Object 的实例
Obj.constructor === Object
// true Obj 对象的构造函数是 Object
```

在这里我原本想 instanceof 既然与构造函数相关那么应该可以通过  constructor 实现。但实际可以看到，通过 constructor 判断的结果并不与 instanceof 的判断完全吻合。

[浅谈 instanceof 和 typeof 的实现原理](https://juejin.im/post/5b0b9b9051882515773ae714);

通过这篇文章了解了 instanceof 的实现
```js
function new_instance_of(leftVaule, rightVaule) { 
    let rightProto = rightVaule.prototype; // 取右表达式的 prototype 值
    leftVaule = leftVaule.__proto__; // 取左表达式的__proto__值
    while (true) {
      if (leftVaule === null) {
            return false;
        }
        if (leftVaule === rightProto) {
            return true;
        }
        leftVaule = leftVaule.__proto__;
    }
}
```
其实 instanceof 主要的实现原理就是只要右边变量的 prototype 在左边变量的原型链上即可。因此，instanceof 在查找的过程中会遍历左边变量的原型链，直到找到右边变量的 prototype，如果查找失败，则会返回 false，告诉我们左边变量并非是右边变量的实例。