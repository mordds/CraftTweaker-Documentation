# 装备槽

一个 IEntityEquipmentSlot 指的是玩家的一个装备槽，如主手槽或装备槽（头盔等）。

## 导入相关包

为了避免发生一些不期而遇的问题（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)），最为安全、也是最为推荐的方式就是导入相关的包。
`import crafttweaker.block.IEntityEquipmentSlot;`

## ZenGetters/ZenMethods

|  Getter   | 类型   |
| :-------: | ------ |
|   index   | int    |
| slotIndex | int    |
|   name    | string |

### 比较

你可以比较两个 IEntityEquipmentSlot 是否相等，
返回一个 bool 值。

```Java
slotOne == slotTwo;
```

## 枚举值

IEntityEquipmentSlot 一共有六个 static 方法，每一个都返回一个该类的实例。

```Java
crafttweaker.entity.IEntityEquipmentSlot.mainHand();
crafttweaker.entity.IEntityEquipmentSlot.offhand();
crafttweaker.entity.IEntityEquipmentSlot.feet();
crafttweaker.entity.IEntityEquipmentSlot.legs();
crafttweaker.entity.IEntityEquipmentSlot.chest();
crafttweaker.entity.IEntityEquipmentSlot.head();
```
