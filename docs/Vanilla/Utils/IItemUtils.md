# 物品实用工具（IItemUtils）

物品实用工具提供了一些对物品的实用工具，可以通过`items`来访问。

## 创建药水

`createPotions` 方法允许你创建自定义药水，将返回一个 [IItemStack](/Vanilla/Items/IItemStack)。
因为参数是一个可变参数，你可以提供一个 `Object[][]` 或多个 `Object[]`。
两种情况中的数组都必须包含：

1. 一个 [IPotion](/Vanilla/Potions/IPotion)
2. 一个 int，即药水等级
3. 一个 int，即药水的持续时间

如果一个 Object[] 不符合上面的条件或顺序，它将会被忽略。

一个例子：

```JAVA
//createPotion(Object[]...);
//createPotion([effect,strength,duration],[effect2, strength2,duration2],...);
//createPotion([[effect,strength,duration],[effect2, strength2,duration2],...]);
val potion = itemUtils.createPotion([[<potion:minecraft:strength>, 1, 1]]);
```

## 通过名称获取物品

这两个方法都返回所有符合正则表达式匹配的 [IItemStack](/Vanilla/Items/IItemStack)[]。
第一个检查物品的 `registryName`，第二个检查物品的 `unlocalizedName`。

```Java
//getItemsByRegexRegistryName(String Regex)
itemUtils.getItemsByRegexRegistryName(".*sword.*"); // 所有在名称中包含 sword 的物品
itemUtils.getItemsByRegexRegistryName(".*thermal.*"); // 所有 thermal expansion/foundation/dynamics 物品

//getItemsByRegexUnlocalizedName(String Regex)
itemUtils.getItemsByRegexUnlocalizedName(".*pink.*"); // 粉的！粉的！（
```

## 创建刷怪蛋

`createSpawnEgg` 方法允许你创建自定义的刷怪蛋，
`customNBT` 是可选的，重写实体 NBT 标签的参数。
返回一个 [IItemStack](/Vanilla/Items/IItemStack)。

```JAVA
//createSpawnEgg(entity, @optional customNBT)
//重写了NBT，生成了一个没有AI的爬行者刷怪蛋！
val egg = itemUtils.createSpawnEgg(<entity:minecraft:sheep>, {EntityTag:{id:"minecraft:creeper",NoAI:1 as byte,PersistenceRequired:1 as byte}});
```
