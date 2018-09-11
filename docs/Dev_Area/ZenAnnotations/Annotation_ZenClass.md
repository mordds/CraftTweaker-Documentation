# Zen 类型

ZenClass 是一种被暴露到 ZenScript 的 Java 类型。

## 例子

[Crafttweaker 的 IItemStack](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/item/IItemStack.java)

```
@ZenClass("crafttweaker.item.IItemStack")
@ZenRegister
public interface IItemStack extends IIngredient {
	//Cut out to keep the page short
}
```

The actual implementation does not need to be annotated.

## 可以应用的类型 || 附加信息

-   所有 Java 类型都可用
-   需要传入一个 String 值作为 ZenScript 中的名称（如 `crafttweaker.item.IItemStack`）。
-   定义类型后，你仍然需要注册。推荐使用 [`@ZenRegister`](/Dev_Area/ZenAnnotations/Annotation_ZenRegister/)。
