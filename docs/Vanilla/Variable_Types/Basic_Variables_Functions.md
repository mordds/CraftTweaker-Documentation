# 基本变量功能

ZenScript 中最常用的就是数值，字符串以及布尔值了。

## 大多数单实例类型

`true == true` 你可以比较两个对象是否相同。
`"Hello" != "World"` 也可以比较两个对象是否不同。

## 字符串

字符串提供了一些功能：

- `"Hello".length` 返回字符串的长度
- `"Hello"[1]` 以另一个字符串的形式返回字符串中的某一个字符。
- `"Hello" in "Hell"` 检查在 `in` 之前的字符串是否包含关键字之后字符串的内容。 也可以用 `has` 代替。
- `"Hel" ~ "lo " + "World"` 你也可以连接字符串。
- `string += "assignAdd"` 也可以使用自增。

同时，Java 中的所有方法也同样适用于 ZenScript 中的字符串！它们有：

- toLowerCase
- toUpperCase
- getBytes
- hashCode
- intern
- isEmpty
- toCharArray
- trim

## 数值

数值提供了一些功能：

- `+-*/%` 基本计算符号 (在 [变量类型处理](Variable_Types) 中有介绍)，也可以使用 `operatorAssign` 符号。
- `0 to 10` 返回一个从 0 到 10 的范围。
- `1~10` 串联数值 (返回 `"110"`).

## 布尔值

布尔值提供了一些功能：

- `true ~ false` (返回 `"truefalse"`).
- `& | ^` 布尔值操作 (与/或/或非).

## 数组/列表

数组和列表都提供了一些功能：

- `array[1]` 返回指定位置的值。
- `array[1] = "Hello"` 设置指定位置的值。
- `array.length` 返回数组长度。
