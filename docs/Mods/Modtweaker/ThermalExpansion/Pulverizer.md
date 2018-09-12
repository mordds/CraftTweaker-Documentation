# 磨粉机

## 包
`mods.thermalexpansion.Pulverizer`

## 添加

```
//mods.thermalexpansion.Pulverizer.addRecipe(输出物品, 输入物品, 能量消耗, 可选-副产物, 可选-副产物概率);
mods.thermalexpansion.Pulverizer.addRecipe(IItemStack output, IItemStack input, int energy, @Optional IItemStack secondaryOutput, @Optional int secondaryChance);

mods.thermalexpansion.Pulverizer.addRecipe(<minecraft:diamond>, <minecraft:stick>, 1500, <minecraft:stone>, 20);
```

## Removal

```
//mods.thermalexpansion.Pulverizer.removeRecipe(输入物品);
mods.thermalexpansion.Pulverizer.removeRecipe(IItemStack input);

mods.thermalexpansion.Pulverizer.removeRecipe(<thermalfoundation:material:136>);
```
