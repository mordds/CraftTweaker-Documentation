# 星辉聚合（Starlight Transmutation）

你可以添加或移除星辉聚合配方。


## 导入
使用`mods.astralsorcery.LightTransmutation`以导入星辉聚合包。 

## 移除
这个方法移除第一个`output`（输出）为传入的[物品堆](/Vanilla/Items/IItemStack/)的配方并且使用`matchStack`（物品堆匹配）以判定是否需要匹配物品附加值。
如果有多个配方可以合成传入的物品，你需要多次使用这个方法！

```JAVA
//mods.astralsorcery.LightTransmutation.removeTransmutation(IItemStack stackToRemove, boolean matchMeta);
//stackToRemove 需要移除的物品堆
//matchMeta 是否需要匹配物品附加值
mods.astralsorcery.LightTransmutation.removeTransmutation(<minecraft:end_stone>, false);
```

## 添加
```
//mods.astralsorcery.LightTransmutation.addTransmutation(IItemStack stackIn, IItemStack stackOut, double cost);
//stackIn 输入的物品
//stackOut 输出的物品
//cost 消耗
mods.astralsorcery.LightTransmutation.addTransmutation(<minecraft:grass>, <minecraft:gold_ore>, 10);
```
