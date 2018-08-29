# 榨汁机（Squeezer）

ModTweaker 允许你添加或移除林业榨汁机配方

## 导入
使用 `mods.forestry.Squeezer` 以导入相关包

## 移除配方

注意：你不能移除填充或清空流体容器（比如林业的罐）的配方

```JAVA
//mods.forestry.Squeezer.removeRecipe(ILiquidStack liquid, @Optional IIngredient[] ingredients);
//liquid 流体
//ingredients 材料（数组）（可选）
mods.forestry.Squeezer.removeRecipe(<liquid:juice>);
mods.forestry.Squeezer.removeRecipe(<liquid:seed.oil>, [<minecraft:wheat_seeds>]);
```


## 添加配方

```JAVA
//mods.forestry.Squeezer.addRecipe(ILiquidStack fluidOutput, IItemStack[] ingredients, int timePerItem, @Optional WeightedItemStack itemOutput);
//mods.forestry.Squeezer.addRecipe(<liquid:lava>, [<minecraft:redstone>], 120);
mods.forestry.Squeezer.addRecipe(<liquid:lava>, [<minecraft:obsidian>], 120, <minecraft:redstone> % 20);
```

| 参数                 | 类型                                                  | 描述                                          |
|---------------------|-------------------------------------------------------|-----------------------------------------------|
| fluidOutput         | [ILiquidStack（流体堆）](/Vanilla/Liquids/ILiquidStack/)| 输出                                          |
| ingredients         | [IItemStack（物品堆）](/Vanilla/Items/IItemStack/)[]    | 输入的物品（数组）                              |
| timePerItem         | 整型                                                  | 催化剂需要的流体数量 |
| itemOutput          | [WeightedItemStack（加权物品堆）](/Vanilla/Items/WeightedItemStack/)| 副产物和概率                        |
