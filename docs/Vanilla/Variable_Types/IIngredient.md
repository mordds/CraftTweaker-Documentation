# 配料

`IIngredient` 代表了配方的配料，
可以是一个 [物品](/Vanilla/Items/IItemStack)，一个 [矿物辞典条目](/Vanilla/OreDict/IOreDictEntry)，一个 [流体](/Vanilla/Liquids/ILiquidStack) 和其他类似的东西。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.item.IIngredient;`

## 使用方法

所以，我们该怎么使用呢？

### 命令字符串

命令字符串是在 ZenScript 表现的方式，可以是尖括号或其他的东西。

```
val item = <minecraft:iron_ingot>;

//输出 "<minecraft:iron_ingot>"
print(item.commandString);
```

### 标记

你可以将一个配料标记并用于 [合成配方](/Vanilla/Recipes/Crafting/Recipe_Functions)，也可以在稍后获得该标记。

```
//Marks the pick with the String Picky
//item.marked(name) <-- Name is a string!
val markedPick = <minecraft:diamond_pickaxe>.marked("Picky");

//prints "Picky"
print(markedPick.mark);
```

### 数量

如果你想使用一个以上的物品，你可以设定 IIngredient 的数量。
这一操作非常简单，你只需要使用乘法，获得数量同样也是可以的。

```
val multipleApples = <minecraft:apple> * 3;

//prints 3
print(multipleApples.amount);
```

### IIngredient 中的“或”

有时你想同时使用 X 或 Y 中的一个配方，但不想为每一种组合都写一个配方？
这就是为什么我们使用了“或”符号：

```java
val item1 = <minecraft:apple>;
val item2 = <minecraft:carrot>;

val either = item1 | item2;
val either2 = item1.or(item2);
```

### 获得匹配的物品/流体

有的时候一个配料能匹配多个物品/流体，比如 [矿物辞典条目](/Vanilla/OreDict/IOreDictEntry) 或者你使用了“或”配料。
第一个方法可以让你获得所有允许的 List<[IItemStack](/Vanilla/Items/IItemStack)> 列表，
第二个方法是同样的，但是返回了一个 [IItemStack](/Vanilla/Items/IItemStack)[] 数组。
有的时候匹配了流体，则返回一个 [ILiquidStack](/Vanilla/Liquids/ILiquidStack) 列表。

```java
//Returns an IItemStack List
//possible items: All iron ingots and the gold ingot from MC
val itemsIngredient = <ore:ingotIron> | <minecraft:gold_ingot>;


//Returns an ILiquidStack List|
//possible liquids: Lava and Water
val liquidsIngredient = <liquid:lava> | <liquid:water>;


for item in itemsIngredient.items{
	//Prints each possible item's Display name
	print(item.displayName);
}

for item in itemsIngredient.itemArray{
	//Prints each possible item's Display name
	print(item.displayName);
}

for liquid in liquidsIngredient.liquids{
	//Prints each possible liquid's Display name
	print(liquid.displayName);
}
```

### 在合成时转换配料

有的时候我们不希望配料在配方中被消耗，或是返回一些其他的副产品，这时候就要用到一些转换器了。

```java
val item = <minecraft:apple>;

//物品不会被消耗并保持在原来的位置
transformedItem = item.reuse();

//物品不会被消耗，但会返回你的物品栏
transformedItem = item.giveBack();

//物品在原来的位置被消耗，给予你其他的物品
transformedItem = item.giveBack(<minecraft:potato>);

//原来位置的物品将会变为其他的物品
transformedItem = item.transformReplace(<minecraft:potato>);

//物品消耗1点耐久
transformedItem = item.transformDamage();

//物品消耗指定耐久
transformedItem = item.transformDamage(3);

//物品被消耗
transformedItem = item.noReturn();

//多个物品被消耗
transformedItem = item.transformConsume(3);
```

### 配料条件

有的时候你希望配料在指定的条件下才消耗耐久，
这时候可以用下面的方法：

```java
val item = <minecraft:apple>;

//物品在消耗耐久后才被接受
var conditionedItem = item.onlyDamaged();

//至少消耗多少耐久
conditionedItem = item.onlyDamageAtLeast(10);

//至多消耗多耐久
conditionedItem = item.onlyDamageAtMost(100);

//耐久在一段范围之间才被接受
conditionedItem = item.onlyDamageBetween(10,100);

//物品在拥有指定NBT的时候才会被接受
//如果你希望物品在JEI的合成中有这条NBT，你需要使用 "withTag(tag)"
conditionedItem = item.onlyWithTag({display: {Name: "Tomato"}});

//物品在拥有指定NBT的时候才会被接受
//在JEI合成中拥有这个NBT
conditionedItem = item.withTag({display: {Name: "Tomato"}});

//物品有多少的时候才会被接受，多和 transformConsume 一同使用。
//注意如果你只使用这个方法，每次合成仍然只消耗一个物品。
conditionedItem = item.onlyStack(32);
```

### 配料匹配

如果你想检查一个物品是否符合你的配料，你可以使用 `match` 方法，返回一个布尔值。
如果配料代表一个流体，将会检查物品是否是该流体的有效容器。

```java
print(<ore:ingotIron>.matches(<minecraft:iron_ingot>));
print(<ore:ingotIron>.matchesExact(<minecraft:iron_ingot>));
```

你也可以检查一个配料是否为另一个配料的补集。

```java
val ingots = <minecraft:iron_ingot> | <minecraft:gold_ingot>;
val goldOre = <ore:ingotIron>;
val ingotGold = <minecraft:gold_ingot>;


//true，gold_ingot 是 ingots 的一员
ingots in ingotGold;

//false，<ore:ingotGold> 中没有 <minecraft:iron_ingot>
goldOre in ingots;
```
