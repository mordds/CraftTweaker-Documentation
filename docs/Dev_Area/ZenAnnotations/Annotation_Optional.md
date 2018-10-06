# 可选

`@Optional` 可以应用到方法的参数上来使其变为可选参数，
在调用时可以被省略。

## 例子

[CraftTweaker 的 IFurnaceManager](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/recipes/IFurnaceManager.java):

```
    @ZenMethod
    void remove(IIngredient output, @Optional IIngredient input);
```

[MCFurnaceManager (Implementation)](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-MC1120-Main/src/main/java/crafttweaker/mc1120/furnace/MCFurnaceManager.java)

```
    @Override
    public void remove(IIngredient output, @Optional IIngredient input) {
        if(output == null)
            throw new IllegalArgumentException("output cannot be null");

        recipesToRemove.add(new ActionFurnaceRemoveRecipe(output, input));
    }
```

理论上来说在实现中 `@Optional` 并不需要被再次应用，但你可以加上来确保有效。
现在你可以用两种办法来调用了：

```
furnace.remove(output); //Input 将会被设置为 null
furnace.remove(output, input);
```

## 省略的参数会被设为什么值？

### 注解无参数

注入 `0`, `false` 或 `null`，取决于参数类型：

数值将会被设为 `0` （除了 boolean 会被设为 false，但那其实也是一种 0），
对象将会被设为 `null`

### 注解有参数

| 字段        | 类型            | 默认值           |
| ----------- | --------------- | ---------------- |
| value       | String          | `""`             |
| methodClass | java.lang.Class | `Optional.class` |
| methodName  | String          | `"getValue"`     |

Optional 注解可以接受默认值，
可以通过 value 字段提供。

如果你需要数值，那么你可以直接设置。

```
@ZenMethod
public static void print(@Optional("heyho") String value) {
    CraftTweakerAPI.logError(value);
}


@ZenMethod
public static void print3(@Optional("1") int value) {
    CraftTweakerAPI.logError(String.valueOf(value));
}
```

如果你需要设置一个非编译期常量 （注解中的成员必须是编译期常量！），那么你需要设置另外两个成员。
这会调用 `methodClass.methodName(value)` 来获得一个默认值。如果没有找到这个方法则仍传入 null。

```
@ZenMethod
public static void print2(@Optional(value = "minecraft:iron_ingot", methodClass = Optionals.class, methodName = "getFromString") IItemStack value) {
    print(value.getDisplayName());
}


public static IItemStack getFromString(String value) {
    return BracketHandlerItem.getItem(value, 0);
}
```

## 哪些参数可以被注解？

所有参数都可以，但可选参数必须要置于最后。一个错误的例子：

```
myMethod(@Optional String name, int number)
```

只传入一个 int 参数会发生错误！
