# 锯木机

## 相关包
`mods.thermalexpansion.Sawmill`

## 添加

```
//mods.thermalexpansion.Sawmill.addRecipe(输出物品,输入物品,所需能量，可选-副产物，可选-副产物概率);
mods.thermalexpansion.Sawmill.addRecipe(IItemStack output, IItemStack input, int energy, @Optional IItemStack secondaryOutput, @Optional int secondaryChance);

mods.thermalexpansion.Sawmill.addRecipe(<minecraft:diamond>, <minecraft:stick>, 1500, <minecraft:stone>, 20);
```

## 移除

```
//mods.thermalexpansion.Sawmill.removeRecipe(输入物品);
mods.thermalexpansion.Sawmill.removeRecipe(IItemStack input);

mods.thermalexpansion.Sawmill.removeRecipe(<minecraft:painting>);
```
