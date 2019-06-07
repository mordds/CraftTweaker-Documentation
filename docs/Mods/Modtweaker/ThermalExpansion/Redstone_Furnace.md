#红石炉

## 相关包
`mods.thermalexpansion.RedstoneFurnace`

## 添加

```
//mods.thermalexpansion.RedstoneFurnace.addRecipe(IItemStack output, IItemStack input, int energy);
//output 输出
//input 输入
//energy 所需能量(RF)
mods.thermalexpansion.RedstoneFurnace.addRecipe(<minecraft:gold_ingot>, <minecraft:iron_ingot>, 3600);
```

## 移除

```
//mods.thermalexpansion.RedstoneFurnace.removeRecipe(IItemStack input);
//input 输入
mods.thermalexpansion.RedstoneFurnace.removeRecipe(<minecraft:gold_ore>);
```
