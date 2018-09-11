# Zen 扩展

ZenExpansion 类似一个 [`@ZenClass`](/Dev_Area/ZenAnnotations/Annotation_ZenClass/)，用来注解一个 ZS 中可用的类型。但它是用来扩展一个已存在的 Zen 类型的。

## 例子

```
@ZenExpansion("crafttweaker.item.IItemStack")
@ZenRegister
public class Expansion {
    @ZenMethod
    public static void print(IItemStack stack) {
        CraftTweakerAPI.logInfo("STACKKKKK: " + stack.getDisplayName());
    }
}
```

这允许了我们调用

```
<minecraft:iron_ingot>.print();
```

第一个参数类型为扩展的目标类型。

_译者注：和 C# 或 Kotlin 中的方法扩展类似_

## 可应用的类型 || 附加信息

-   所有方法的第一个参数类型都应为扩展的目标类型，且都应该是 `public static` 的访问权限。
-   所有 Java 类型都可用。
-   注解需要指定一个已经存在的 Zen 类型名称 (如 `crafttweaker.item.IItemStack`)。
-   在定义一个 ZenExpansion 之后，你仍然需要注册。推荐使用 [`@ZenRegister`](/Dev_Area/ZenAnnotations/Annotation_ZenRegister/)。
