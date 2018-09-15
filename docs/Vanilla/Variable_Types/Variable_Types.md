# 变量类型处理

你肯定在 CraftTweaker 对于变量的处理上有了一些混乱，想知道 CT 是怎么分清数值，物品和矿物辞典条目的？

最基本的变量定义方式就是 `var name = value;`。
它创建了一个变量并赋予变量看起来最适合这个值的类型。

## 将变量转换为指定的类型

更复杂的脚本要求你从一个类型转换为另一个类型。
例如：下面的代码会报错：

```java
var test;

test = <minecraft:dirt>;
recipes.remove(test);
```

所以为什么这行不通呢？
这是因为 CT 将定义时未赋初值的变量设定为了 IAny 类型。
这种类型是为了方便一些配方处理程序而引入的（这样就不用转换来转换去了），它没有任何功能，所以它有时弊大于利。它相当于 ZenScript 中所有类的基类。

回到我们的主题：
如何解决这个问题呢？你会想到将变量转换为用于物品的 `IItemStack` 类型。
不幸的是，有些类型需要被导入，而这个类型就是其中一员。

```java
import crafttweaker.item.IItemStack;
var test as IItemStack;

test = <minecraft:dirt>;
recipes.remove(test);
```

## 变量类型

这是一个大概的变量类型列表

| 类名 （CT 中的名称）                                  | 解释                                                               | 例子                                           | 导入                                      |
| ----------------------------------------------------- | ------------------------------------------------------------------ | ---------------------------------------------- | ----------------------------------------- |
| Integer (int)                                         | 32 位整数                                                          | `var test = 10 as int;`                        |                                           |
| [IItemStack](/Vanilla/Items/IItemStack)               | 单个物品                                                           | `var test = <minecraft:dirt> as IItemStack;`   | import crafttweaker.item.IItemStack;      |
| [IIngredient](/Vanilla/Variable_Types/Variable_Types) | 单个或多个物品 (如 `<minecraft:dirt>`, `<ore:ingotIron>`,...)      | `var test = <minecraft:dirt> as IIngredient;`  | import crafttweaker.item.IIngredient;     |
| [IOreDictEntry](/Vanilla/OreDict/IOreDictEntry)       | 矿物辞典中的多个物品 (如 `<ore:ingotIron>`, `<ore:ingotGold>`,...) | `var test = <ore:ingotIron> as IOreDictEntry;` | import crafttweaker.oredict.IOreDictEntry |
| Boolean (bool)                                        | 真或假                                                             | `var test = false as bool;`                    |                                           |
| Byte (byte)                                           | 0 ~ 255 之间的整数                                                 | `var test = 125 as byte;`                      |                                           |
| Floating Point (float)                                | 单精度浮点数                                                       | `var test = 1.25 as float;`                    |                                           |
| Double Precision (double)                             | 双精度浮点数                                                       | `var test = 1.25 as double;`                   |                                           |
| Long (long)                                           | 64 位整数                                                          | `var test = 30 as long;`                       |                                           |
| Null (null)                                           | 空                                                                 | `var test = null;`                             |                                           |
| Short (short)                                         | 16 位整数                                                          | `var test = 16 as short;`                      |                                           |
| String (string)                                       | 字符串，""中的任何东西都是字符串所以你基本不用转换                 | `var test = "Hello World!" as string;`         |                                           |
| Void (void)                                           | 跟函数打交道的时候才会用到，空返回值                               | `var test as void;`                            |                                           |
| [ILiquidStack](/Vanilla/Liquids/ILiquidStack)         | 对于流体来说的一种 ItemStack                                       | `var test = <liquid:water> as ILiquidStack;`   | import crafttweaker.liquid.ILiquidStack;  |
