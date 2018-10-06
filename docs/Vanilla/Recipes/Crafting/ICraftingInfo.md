# 合成信息

IcraftingInfo（合成信息）对象包含所有合成过程中的信息:

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.recipes.ICraftingInfo`

## ZenGetters

| ZenGetter             |                                                                    |                                                    |
| --------------------- | ------------------------------------------------------------------ | -------------------------------------------------- |
| `inventory（物品栏）` | [ICraftingInventory](/Vanilla/Recipes/Crafting/ICraftingInventory) | 合成所使用的物品栏                                 |
| `player（玩家）`      | [IPlayer](/Vanilla/Players/IPlayer)                                | 合成的玩家                                         |
| `dimension（维度）`   | int                                                                | 合成所在的维度                                     |
