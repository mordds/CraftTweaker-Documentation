# 物品:
物品是 CompatSkills 加入的需求，允许你用物品作为需求锁定游戏内容。通过在主手或副手持有指定物品或带有 NBT 数据的物品或某个模组的物品解锁。
物品的用法如下：
```
例子:
// 指定模组的任意物品
stack|modid

// 方块实体附加值为0的指定物品
stack|modid:item

// 有指定方块实体附加值的指定物品（* = 任意方块实体附加值）
stack|modid:item:meta

// 指定 NBT 数据的任意物品
stack||NBT as JSON

// 指定 NBT 数据且来自指定模组的任意物品
stack|modid|NBT as JSON

// 指定 NBT 数据且方块实体附加值为0的指定物品
stack|modid:item|NBT as JSON

// 指定 NBT 数据且有指定方块实体附加值的指定物品
stack|modid:item:meta|NBT as JSON

//modid 模组 id
//item 物品名称
//meta 方块实体附加值
//NBT as JSON JSON 格式的 NBT 数据

// 实例:
stack|minecraft
stack|minecraft:iron_pickaxe
stack|minecraft:iron_pickaxe:*

//有精准采集魔咒的物品
stack||{ench:[{id: 33s}]} 

//时运强化的匠魂物品
stack|tconstruct|{ench:[{id: 35s}]} 

stack|minecraft:iron_sword|{ench:[{id: 17s}]}
stack|minecraft:iron_sword:*|{ench:[{id: 17s}]}
```
