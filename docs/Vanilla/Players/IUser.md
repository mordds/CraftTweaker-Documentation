# 用户（IUser）

IUser 接口是用来在内部组合不同的用户类型的，例如将服务端控制台，普通用户，和命令方块组合在一个类型中。
你大概很少会用到它。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.player.IUser;`

## 扩展 ICommandSender

IUser 继承了 [ICommandSender](/Vanilla/Commands/ICommandSender)。这意味着所有 [ICommandSender](/Vanilla/Commands/ICommandSender) 中的成员也同样适用于 IUser。

## 方法

目前 IUser 没有定义任何方法。
