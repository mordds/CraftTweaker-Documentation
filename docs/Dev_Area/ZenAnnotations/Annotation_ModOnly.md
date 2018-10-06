# 前置模组

`@ModOnly` 和它的名字一样简单，仅当一个模组加载后才注册这个 Zen 类型。

## 例子

[Crafttweaker Test Project ModOnly](https://github.com/jaredlll08/CraftTweaker/tree/1.12/CraftTweaker2-MC1120-Tests/src/main/java/crafttweaker/tests/wiki/ModOnlyWiki.java)

```
@ModOnly(value = "mcp")
@ZenClass(value = "crafttweaker.tests.modOnly")
@ZenRegister
public class ModOnlyWiki {
	@ZenMethod
	public static void print() {
		CraftTweakerAPI.logInfo("print issued");
	}
}
```

## 可以被注解的类型 || 附加信息

-   你可以应用到同时拥有 [`@ZenRegister` 注解](/Dev_Area/ZenAnnotations/Annotation_ZenRegister/) 的 Java 类型。理论上来说它们都能被注册，但只有条件满足后才会有效果。
-   注解需要一个 modid 来调用 `isModLoaded(annotation.getValue())` 以获取模组是否加载
