# Zen 自动注册

ZenRegister 注解可用来自动注册 [`@ZenClass`](/Dev_Area/ZenAnnotations/Annotation_ZenClass/) 或 [`@ZenExpansion`](/Dev_Area/ZenAnnotations/Annotation_ZenExpansion/) 注解。  
这是在 ZenScript 中推荐的注册方式。

## 例子

[Crafttweaker 的 IIngredient](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/item/IIngredient.java)

```
@ZenClass("crafttweaker.item.IIngredient")
@ZenRegister
public interface IIngredient {
	...
}
```
