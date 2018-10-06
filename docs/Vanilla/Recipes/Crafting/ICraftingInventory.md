# 合成物品栏（ICraftingInventory）

合成物品栏返回了一个正在执行合成的物品栏之中的所有信息。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.recipes.ICraftingInventory`

## ZenGetters

| ZenGetter    | 返回类型                                    | 描述                   |
| ------------ | ------------------------------------------- | ---------------------- |
| `player`     | [IPlayer](/Vanilla/Players/IPlayer)         | 持有物品栏的玩家       |
| `size`       | int                                         | 物品栏大小             |
| `width`      | int                                         | 物品栏宽度             |
| `height`     | int                                         | 物品栏高度             |
| `stackCount` | int                                         | 当前一共有多少个物品   |
| `items`      | [IItemStack[][]](/Vanilla/Items/IItemStack) | 合成台物品（二维数组） |
| `itemArray`  | [IItemStack[]](/Vanilla/Items/IItemStack)   | 合成台物品（一维数组） |

## ZenMethods

下面的方法是可用的：

`inventory.getStack(index)` 返回一个在指定 int 位置的 [IItemStack](/Vanilla/Items/IItemStack)，如果没有则返回 null。
`inventory.setStack(index, item)` 在指定 int 位置设置一个 IItemStack，如果设置为 null 则清空该位置的物品。

坐标原点为左上角，行和列均为 int 值:
`inventory.getStack(row, column)` 返回一个在指定位置的 [IItemStack](/Vanilla/Items/IItemStack)，如果没有则返回 null。
`inventory.setStack(row, column, item)` 在指定位置设置一个 IItemStack，如果设置为 null 则清空该位置的物品。
