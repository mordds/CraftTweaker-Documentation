# Zen 说明文档

`@ZenDoc` 注解允许开发者在 `/ct dumpZS` 命令中提供附加信息。
结果看起来像这样：

![img](assets/zenDoc.png)

_（译者注：那个########中的内容就是附加信息）_

## 例子

[Crafttweaker Test Project ZenDoc](https://github.com/jaredlll08/CraftTweaker/tree/1.12/CraftTweaker2-MC1120-Tests/src/main/java/crafttweaker/tests/wiki/ZenDocWiki.java)

```
@ZenClass(value = "crafttweaker.tests.zenDoc")
@ZenRegister
public class ZenDocWiki {
	@ZenMethod
	@ZenDoc("This prints a warning")
	public static void print() {
		CraftTweakerAPI.logWarning("Print invoked!");
	}
}
```

## 可以被应用的方法 || 附加信息

-   所有静态/非静态方法都可用。
-   只会影响 [`/ct dumpzs`](/Vanilla/Commands/) 中导出的 HTML 文件。
-   需要传入一个 String 值作为导出的附加信息。
