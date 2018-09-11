# Zen 操作符重载

被 `@ZenOperator` 注解的方法不能被正常的 `instance.method(parameters)` 调用，但是可以使用 `+`, `!` 等的标记调用。

## 例子

[Crafttweaker 的 IData](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/data/IData.java)

```
@ZenClass("crafttweaker.data.IData")
@ZenRegister
public interface IData {

    @ZenOperator(OperatorType.ADD)
    IData add(IData other);

    @ZenOperator(OperatorType.SUB)
    IData sub(IData other);

    ...
}
```

## 可应用的方法 || 附加信息

-   所有非静态方法都可用，但你只能指定一种 [操作符类型](/Dev_Area/ZenOperators/)。
-   你应该返回和参数相同的类型 （不要用物品 + 物品 = 流体这种重载！）
-   你可以在 [这里](/Dev_Area/ZenOperators/) 找到所有可用的操作符类型。
