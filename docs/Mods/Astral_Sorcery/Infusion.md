# 星能聚合配方（Starlight Infusion Recipe）
你可以添加或移除聚合配方。

## 导入
使用`mods.astralsorcery.StarlightInfusion`以导入星能聚合相关包。

## 移除
这个方法移除第一个`output（输出）`为传入的[物品堆](/Vanilla/Items/IItemStack/)的配方。
如果有多个配方可以合成传入的物品，你需要多次使用这个方法！
```JAVA
//mods.astralsorcery.StarlightInfusion.removeInfusion(IItemStack output);
//output：输出
mods.astralsorcery.StarlightInfusion.removeInfusion(<minecraft:ice>);
```

## 添加
```JAVA
//mods.astralsorcery.StarlightInfusion.addInfusion(IItemStack input, IItemStack output, boolean consumeMultiple, float consumptionChance, int craftingTickTime);
//input:输入
//output：输出
//consumeMultiple:是否消耗多个星能液
//consumptionChance:消耗概率
//craftingTickTime:合成时间
mods.astralsorcery.StarlightInfusion.addInfusion(<astralsorcery:itemjournal>, <minecraft:bow>, false, 0.7, 200);
```
