# 三维浮点位置

在 Minecraft 中，一个 `Position3f` 存储了 x，y，z 这样的三维位置。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.util.Position3f;`

## 获得 Position3f 实例

你可以使用下列方法获得一个实例：

- [玩家](/Vanilla/Players/IPlayer) 实例中的 `position` ZenGetter
- 下面的构造器
- [方块位置](/Vanilla/World/IBlockPos) 中的 Position3f 转换器

## Position3f 构造器

你可以自己使用该方法来创建一个 Position3f 实例:

```JAVA
crafttweaker.util.Position3f.create(float x, float y, float z);
```

## ZenGetters and ZenSetters

| ZenGetter | ZenSetter | 描述            |
| --------- | --------- | --------------- |
| x         | x         | 返回位置的 x 值 |
| y         | y         | 返回位置的 y 值 |
| z         | z         | 返回位置的 z 值 |

## 转换到 IBlockPos

你可以用下列两种方式来转换到一个 [IBlockPos](/Vanilla/World/IBlockPos) 实例：
记住，使用 `as` 你将需要 [导入](/AdvancedFunctions/Import) 你想要转换到的类型，除非你使用它的全名。

```
posThree.asBlockPos();
posThree as IBlockPos;
```
