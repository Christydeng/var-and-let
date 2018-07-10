# var-and-let
var 和 let 的区别

作用域更加清晰不存在变量作用域自动提升的问题造成变量值被覆盖的问题，例如：let a = 1;

var b = 1;
if (true) {
let a = 2;
var b = 2;
}

console.log(a) // a is 1
console.log(b) // b is 2

作用域更容易控制let 的作用域是根据代码块（enclosing block）来判定的，而 var 的作用域是根据函数块（function block）来判定的。这样的话，如果我们的变量都使用 let/const 来声明，那么以前的立即执行函数就不需要了，我们只要加一个代码块就好了，例如：{
let a = 1;
}

console.log(a) // a is not defined

Runtime自动检查重复声明的函数并报错在同一个作用域内不允许重复声明变量，
例如
if (true) {
let a = 1;
let a = 2;
}

Runtime会报错：Uncaught SyntaxError: Identifier 'a' has already been declared有了更加清晰的作用域，我们的代码就能够更好被预测，也更好维护。有了更容易控制的作用域可以让我们减少很多立即执行的函数。Runtime的自动检查可以避免不必要，甚至是错误的代码声明。


链接：https://www.zhihu.com/question/47456978/answer/106069482
