# 反转需求:

## [NOTICE]
Inverted Requirements are Deprecated and is replaced internally by the NOT-Logical Operator.
This means that the inverted requirements are automatically converted in-code into a NOT-Operator.
Please refrain from using this requirement type, they are still included for **Legacy Support!**

## 反转需求:
反转需求是仅在 CompatSills 1.4.0版本及以后的特性！
只要不满足需求内容就可以解锁游戏内容。
反转的技能需求会在当玩家小于指定的等级时解锁。
反转需求的用法如下:
```
例子:
!adv|
!dim|
!stage|
!skill|
!trait|


实例:
!adv|minecraft:husbandry/plant_seed
!dim|0
!stage|test
!skill|reskillable:building|15
!trait|reskillable:battle_spirit
```
