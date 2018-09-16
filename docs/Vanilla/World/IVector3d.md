# 三维向量

`Vector3d` 是一个用三个 double 来表示一个三维向量的类型，
这里有一些实用的方法。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.world.IVector3d`

## ZenGetters

| ZenGetter  | 类型      |
| ---------- | --------- |
| x          | double    |
| y          | double    |
| z          | double    |
| normalized | IVector3d |

## ZenMethods

- double dotProduct(IVector3d other);
- IVector3d crossProduct(IVector3d other);
- IVector3d subtract(IVector3d other);
- IVector3d add(IVector3d other);
- double distanceTo(IVector3d other);
- IVector3d scale(double factor);
