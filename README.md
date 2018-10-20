# eslint-
用过Airbnb、Standard后，推荐Prettier来统一代码风格

我曾经以为，程序员有自己独特的代码风格挺好的。因为，一个成熟的程序员应该清楚，好的代码应该是怎样的。

一些示例
示例1：
读了The Programmers’ Stone之后，我把大括号这样写：

if (food === 'pizza')
{
    alert('Pizza ;-)');  
}
else
{  
    alert('Not pizza ;-(');
}
但是，我意识到在前端社区里，也许只有我一个人这样写的。而其他人都是这样写的：

if (food === 'pizza') {
    alert('Pizza ;-)');  
} else {
    alert('Not pizza ;-(');
}
或者这样：

if (food === 'pizza') {
    alert('Pizza ;-)');  
}
else {  
    alert('Not pizza ;-(');
}
于是，我改变了风格，采用了最后一种写法。

示例2
将多个方法链接起来时，我喜欢这样写：

function foo(items) {
  return items
    .filter(item => item.checked)
    .map(item => item.value)
  ;
}
示例3
读了Why you should enforce Dangling Commas for Multiline Statements，我意识到了trailing commas写法更加易于重构：

const food = [
  'pizza',
  'burger',
  'pasta',
]
但是，这种写法非常少见。我审查过的代码中，没人这样写。于是，我只能放弃这种写法，向现实世界低头。

示例4
我还有一个不合群的习惯。在行尾写代码注释之前，我习惯敲2个空格：

const volume = 200;  // ml
我觉得这样写好看些。但是，这会导致代码不一致，因为其他人只敲一个空格。

JavaScript开发者是怎样做的
很遗憾，JavaScript没有官方的代码风格。业界有一些流行的代码风格，比如Airbnb和Standard。使用它们的话，团队成员之间的代码会更易读。

你也可以使用ESLint 来统一风格。但是它并不能保证代码100%一致。比如，ESLint的Airbnb配置，只能统一示例1的代码风格，而不能统一后面两者。

JavaScript开发者应该怎么做？
有一些语言有非常严格的代码风格，并且有工具可以用于统一风格。因此，开发者不需要浪费时间去争论代码风格的优劣。例如，Reason语言的Refmt，和Rust语言的Rustfmt。

现在，JavaScript终于有了一个解决方案。有一个新工具，叫做Prettier，它运用自身的规则将你的的代码重新格式化。无论你之前的代码风格是怎样。

我们不妨试用一下Prettier。

输入代码是这样的：

if (food === 'pizza')
{
    alert('Pizza ;-)');  
}
else
{  
    alert('Not pizza ;-(');
}

function foo(items) {
  return items
    .filter(item => item.checked)
    .map(item => item.value)
  ;
}

const food = [
  'pizza',
  'burger',
  'pasta',
]
Prettier处理之后的代码是这样的：

if (food === "pizza") {
  alert("Pizza ;-)");
} else {
  alert("Not pizza ;-(");
}

function foo(items) {
  return items.filter(item => item.checked).map(item => item.value);
}

const food = ["pizza", "burger", "pasta"];
也许，你并不喜欢这种风格。比如，我不喜欢else放在大括号后面，也不喜欢把链式方法全部写在同一行。但是，我发现使用Prettier有很多益处：

几乎不需要做决定，因为 Prettier的配置选项很少。
团队成员不需要为规则去争论。
开源代码开发者不需要去学习项目的代码风格。
不需要去修复ESLint报告的风格问题。
保存文件的时候可以自动统一风格。
结论
Prettier已经被一些非常流行的项目比如React和Babel采用了。对于我自己的项目，我已经开始从自己的个性化风格全部转为Prettier风格。相比于Airbnb代码风格，我更推荐Prettier。

刚开始，我会觉得Prettier风格非常差。但是，当我发现自己需要手动去调整代码风格时，我意识到Prettier真的非常好用。

Prettier可以在保存文件的时候可以自动统一风格：
