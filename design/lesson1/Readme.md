# 面向对象的JavaScript

<a name="e05dce83"></a>
### 简介

---
JavaScript 是一门**动态类型**语言，并且不同于一般的面向对象语言（如 Java），它使用原型委托（原型链）的方式来实现继承。


<a name="226b0912"></a>
### 类型

---
编程语言按数据类型大体可分为两类：静态类型语言、动态类型语言。

**静态类型语言**<br />**<br />静态类型语言在编译时便已确定变量的类型。

优点：在程序编译时就能发现类型不匹配的错误，执行速度相对较快。<br />缺点：一定要为每个变量声明数据类型，比较繁琐。

**动态类型语言**

动态类型语言在程序运行时，待变量被赋值，才会具有某种类型。

优点：编写的代码数量更少，可以将更多的精力放在业务逻辑上。<br />缺点：无法保证变量的类型，程序运行期间可能发生和类型相关的错误。

**鸭子类型**

鸭子类型：如果它走起路来像鸭子，叫起来像鸭子，那么它就是鸭子。

 
<a name="154ae683"></a>
### 多态

---
多态思想就是将 “做什么” 和 “谁去做” 分离开来，要现实这一点，首先要将类型之间的耦合消除。<br />在 JavaScript 中，对象的多态性是天生的，不同于 Java 中使用向上转型来获得多态。

<a name="6912abd3"></a>
### 封装

---
封装的目的是将细节隐藏，对其他对象而言，自己的内部是不可见的。

**封装数据**<br />通过函数作用域模拟封装私有变量。<br />es6 中提供新支持的块级作用域。

**封装实现**<br />**封装使得对象之间的耦合变松散，对象之间之通过 API 接口通信。<br />用户并不关心函数内部现实，只要它提供的功能是正确的便可以了。

**封装变化**<br />**<br />封装程序中容易变化的部分。


<a name="lkZbl"></a>
### 原型模式

---
原型模式和基于原型继承的 JavaScript 对象系统，原型模式不单是一种设计模式，也被称为一种编程泛式。<br />站在设计模式的角度，原型模式是一种用于创建对象的模式。


**克隆**<br />**<br />原型模式创建对象，并不通过类来创建，而是使用克隆的方式来创建出一个一摸一样的对象。<br />原型模式的真正目的并非是得到一个一模一样的对象，而是提供了一种便捷的方式创建某个类型的对象，克隆只是创建这个对象的过程和手段。

**原型编程泛式的一些规则**<br />**<br />**原型委托**机制就是**原型继承**的本质。

```javascript
var Animal = function(){}
Animal.prototype.sound = function () {
  console.log('animal sound xixixi hahaha')
}

var Dog = function(){}
Dog.prototype = Object.create(Animal)

var dog = new Dog()

console.log(dog.sound())
// animal sound xixixi hahaha
```

