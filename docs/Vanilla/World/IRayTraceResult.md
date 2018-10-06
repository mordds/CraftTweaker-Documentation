# 射线追踪结果

当玩家看向/点击的时候，他会有一个目标，但不一定点中了（点空气），这样的结果就是一个 IRayTraceResult。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.world.IRayTraceResult`

## ZenGetters

你可以获取下列信息，注意所有非 bool 字段都是可 null 的！

| 名称     | 类型                                  |
| -------- | ------------------------------------- |
| isMiss   | bool                                  |
| isEntity | bool                                  |
| isBlock  | bool                                  |
| entity   | [IEntity](/Vanilla/Entities/IEntity)  |
| blockPos | [IBlockPos](/Vanilla/World/IBlockPos) |
| sideHit  | [IFacing](/Vanilla/World/IFacing)     |
