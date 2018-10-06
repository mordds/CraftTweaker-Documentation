# 玩家（IPlayer）

玩家接口允许你查看一些属性并与它们交互。
多用于事件处理器和合成方法中。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.player.IPlayer;`

## 扩展 IEntityLivingBase 和 IUser

IPlayer 继承了 [IEntityLivingBase](/Vanilla/Entities/IEntityLivingBase) 和 [IUser](IUser)。这意味着 [IEntityLivingBase](/Vanilla/Entities/IEntityLivingBase) 以及 [IUser](IUser) 中的成员也同样适用于 IPlayer。

## Zengetters

| Zengetter     | 说明                        | 返回类型                                | 使用方法               |
| ------------- | --------------------------- | --------------------------------------- | ---------------------- |
| id            | 返回玩家的 UUID             | string                                  | `player.id`            |
| name          | 返回玩家的名称              | string                                  | `player.name`          |
| data          | 返回玩家的数据              | [IData](/Vanilla/Data/IData)            | `player.data`          |
| xp            | 返回/设置玩家经验值         | int                                     | `player.xp`            |
| hotbarSize    | 返回玩家的快捷槽大小        | int                                     | `player.hotbarSize`    |
| inventorySize | 返回玩家的物品栏大小        | int                                     | `player.inventorySize` |
| currentItem   | 返回玩家当前手持的物品      | [IItemStack](/Vanilla/Items/IItemStack) | `player.currentItem`   |
| creative      | 返回玩家是否为创造模式      | bool                                    | `player.creative`      |
| adventure     | 返回玩家是否为冒险模式      | bool                                    | `player.adventure`     |
| x             | 返回玩家在世界中的 X 坐标值 | double                                  | `player.x`             |
| y             | 返回玩家在世界中的 Y 坐标值 | double                                  | `player.y`             |
| z             | 返回玩家在世界中的 Z 坐标值 | double                                  | `player.z`             |
| position      | 返回/设置玩家在世界中的位置 | [Position3f](/Vanilla/Utils/Position3f) | `player.position`      |
| foodStats     | 返回玩家的食物状态          | [IFoodStats](IFoodStats)                | `player.foodStats`     |

## ZenMethods

| ZenMethod                | 参数类型                                | 说明                                 | 例子                                     |
| ------------------------ | --------------------------------------- | ------------------------------------ | ---------------------------------------- |
| removeXP(XPtoRemove)     | int                                     | 移除玩家的经验等级。                 | `player.removeXP(1)`                     |
| update(IData)            | [IData](/Vanilla/Data/IData)            | 向玩家的 IData 中更新数据。          |                                          |
| sendChat(Message)        | string 或 IChatMessage                  | 向玩家发送聊天信息。                 | `player.sendChat("Hello my old friend")` |
| getHotbarStack(index)    | int                                     | 在玩家的快捷槽中获取指定位置的物品。 | `player.getHotbarStack(3)`               |
| getInventoryStack(index) | int                                     | 在玩家的物品栏中获取指定位置的物品。 | `player.getInventoryStack(3)`            |
| give(item)               | [IItemStack](/Vanilla/Items/IItemStack) | 给予玩家一个 IItemStack。            | `player.give(<minecraft:gold_ingot>)`    |
| teleport(position)       | [Position3f](/Vanilla/Utils/Position3f) | 在同一个世界中传送玩家。             | `player.teleport(position)`              |
| executeCommand(raw)      | string                                  | 以玩家身份执行一个指令。             | `player.executeCommand("kill")`          |
