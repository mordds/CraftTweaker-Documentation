# 流体定义（ILiquidDefinition）

流体定义，定义着 [流体堆](ILiquidStack) 所包含的流体。  
不同于流体堆，这个接口能够允许你修改流体属性。

## 导入相关包

为了避免发生一些不期而遇的问题（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)），最为安全、也是最为推荐的方式就是导入相关的包。
`import crafttweaker.liquid.ILiquidDefinition;`

## 方法

仔细想想我们能做些什么？

### 乘号

将一个 ILiquidDefinition 用乘法会返回一个有着指定 mB 的 [ILiquidStack](ILiquidStack)，即实例化一个 ILiquidStack。

```java
val def = <liquid:lava>.definition;

// 本质是一样的
val bucketOfLava = def * 1000;
val bucketOfLava1 = <liquid:lava> * 1000;
```

## 获取和设置流体属性

我们已经知道 ILiquidDefinition 代表了一个流体，所以你可以获取和设置它的一些属性。
查看下面的表格来获取更多信息。

像表格所说的一样，你在 ILiquidDefinition 最后使用 ZenGetter/Setter 来设置它的属性。
但一些属性只有 Getter 而没有 Setter，所以你可能需要依赖于其他的属性来调整它们。

这些 Setter 只对注册表中的流体有效，而不对世界中已存的流体有效。你大概只需要补全用于 [Tinkers' Construct 熔炼炉燃料](/Mods/Modtweaker/TConstruct/Fuel) 的流体温度属性。

```java
val definition = <liquid:lava>.definition;

//Zengetter: luminosity
val lavaL = definition.luminosity;

//Zensetter: luminosity
definition.luminosity = 0;
```

| Zengetter   | Zensetter   | 这是什么？         | 值类型  |
| ----------- | ----------- | ------------------ | ------- |
| name        |             | 未本地化的流体名称 | string  |
| displayName |             | 本地化的流体名称   | string  |
| luminosity  | luminosity  | 流体亮度           | int     |
| density     | density     | 流体密度           | int     |
| temperature | temperature | 流体温度           | int     |
| viscosity   | viscosity   | 流体粘度           | int     |
| gaseous     | gaseous     | 流体是否为气体     | boolean |
