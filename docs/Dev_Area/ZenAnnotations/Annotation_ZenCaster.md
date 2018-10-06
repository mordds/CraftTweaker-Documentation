# Zen 类型转换

ZenCaster 使一个方法可以作为 `as` 标记调用的类型转换方法，用来将一个 Zen 类型转换为另一个 Zen 类型 (如 [Strings 转为 IData](https://github.com/jaredlll08/CraftTweaker/blob/30793645d58adeed12dfff50f31206a63a50d8de/CraftTweaker2-API/src/main/java/crafttweaker/zenscript/expand/ExpandString.java#L30-L33)).

## 例子

```
@ZenExpansion("crafttweaker.item.IItemStack")
@ZenRegister
public class Expansion {
    @ZenMethod
    public static void print(IItemStack stack) {
        CraftTweakerAPI.logInfo("STACKKKKK: " + stack.getDisplayName());
    }

    @ZenCaster
    public static IOreDictEntry asOreDict(IItemStack stack) {
    	return stack.getOres().get(0);
    }
}
```

If someone now would call this, they would get an oreDictEntry:

```
val oreDict = <minecraft:iron_ingot> as IOreDictEntry;
```

## 可以应用的方法 || 附加信息

-   你可以应用到所有非静态方法 （除非在 ZenExpansion 中，因为它们只包含静态方法）
-   在 [ZenExpansion](/Dev_Area/ZenAnnotations/Annotation_ZenExpansion/) 中需要多一个参数（代表 this），在 [ZenClass](/Dev_Area/ZenAnnotations/Annotation_ZenClass/) 中不需要。
-   不要在 [ZenClasses](/Dev_Area/ZenAnnotations/Annotation_ZenClass/) 中过多依赖这一方法，它们应该只在 [ZenExpansions](/Dev_Area/ZenAnnotations/Annotation_ZenExpansion/) 中被定义。
