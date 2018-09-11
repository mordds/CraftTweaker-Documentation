# 尖括号处理器

尖括号处理器可以在 `<tokens>` 中处理 [ZenTokens](/Dev_Area/ZenTokens/)。
ZS 会将所有标记加到一个列表当中并在尖括号处理器中寻找一个非 `null` 的结果。

注解的类需要实现 [IBracketHandler](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/zenscript/IBracketHandler.java)

## 例子

[CraftTweaker Test Project Bracket Handler](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-MC1120-Tests/src/main/java/crafttweaker/tests/wiki/BracketWiki.java)

```
@BracketHandler(priority = 34)
@ZenRegister
public class BracketWiki implements IBracketHandler{

	@Override
	public IZenSymbol resolve(IEnvironmentGlobal environment, List<Token> tokens) {
		if ((tokens.size() < 3)) return null;
		if (!tokens.get(0).getValue().equalsIgnoreCase("devBracket")) return null;
		if (!tokens.get(1).getValue().equals(":")) return null;

		return new devSymbol(tokens);
	}


	private class devSymbol implements IZenSymbol {

		private final String value;
		public devSymbol(List<Token> tokens) {
			StringBuilder sB = new StringBuilder();
			tokens.stream().map(Token::getValue).forEach(sB::append);
			this.value = sB.toString().replaceAll(":", " ");
		}

		@Override
		public IPartialExpression instance(ZenPosition position) {
			return new ExpressionString(position, "DevSymbol: ".concat(value));
		}

	}

}
```

## 可以被注解的类型 || 附加信息

-   你可以应用到所有实现了 [IBracketHandler](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/zenscript/IBracketHandler.java) 的类型。
-   你可以赋予一个优先度 (如 `priority = 100`)，优先度越高越先被处理，CT 的优先度默认都为 100。
-   你仍然需要注册这个类，推荐使用 [`@ZenRegister`](/Dev_Area/ZenAnnotations/Annotation_ZenRegister/)。
-   如果你的处理器不能处理这些标记，你应该返回 `null`。
