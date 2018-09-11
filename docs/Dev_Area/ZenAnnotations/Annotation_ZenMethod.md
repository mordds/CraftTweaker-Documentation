# Zen 方法

Zen 方法是暴露在 ZenScript 中的 Java 方法。

静态方法可以使用 [Zen 类型的名称](/Dev_Area/ZenAnnotations/Annotation_ZenClass/) 来调用，否则你需要使用 `object.methodName(arguments,..);`。
ZenMethod 注解也可以和其他 [注解](/Dev_Area/ZenAnnotations/ZenAnnotation/) 同时使用，例如 [Zen 操作符](/Dev_Area/ZenAnnotations/Annotation_ZenOperator/).

## 可以被注解的方法 || 附加信息

-   所有方法都可用。
-   在 [ZenExpansion](/Dev_Area/ZenAnnotations/Annotation_ZenExpansion/) 中的注解需要一个参数，代表了扩展的目标类型。
-   在 [ZenExpansion](/Dev_Area/ZenAnnotations/Annotation_ZenExpansion/) 中注解一个非扩展静态方法时 （如一个工厂方法）那么你需要使用 [ZenMethodStatic](/Dev_Area/ZenAnnotations/ZenMethodStatic/) 来代替。

## 例子

```
@ZenClass(value = "crafttweaker.tests.devWikiTest")
@ZenRegister
public class DevWikiTest {

	//statics which will be called using crafttweaker.tests.devWikiTest.methodName(arguments);
	@ZenMethod
	public static DevWikiTest staticMethod(int arg1) {
		return new DevWikiTest(arg1);
	}

	@ZenMethod
	public static void staticMethod2() {
		CraftTweakerAPI.logInfo("staticMethod2 called!");
	}

	@ZenMethod
	public static void staticMethodVarArg(int... args) {
		CraftTweakerAPI.logInfo("staticMethod3 called with " + args.length + " arguments");
	}



	//nonstatics which sill be called using instance.methodName(arguments);
	@ZenMethod
	public int getValue() {
		return value;
	}

	@ZenMethod
	public void print() {
		CraftTweakerAPI.logInfo("DevWikiTest Object with value " + value);
	}

	@ZenMethod
	public void printWithVarArg(int... args) {
		CraftTweakerAPI.logInfo("Nonstatic called with " + args.length + " arguments");
	}


	private final int value;

	public DevWikiTest(int value) {
		this.value = value;
	}
}
```

ZS 脚本

```
val instance = crafttweaker.tests.devWikiTest.staticMethod(10);
crafttweaker.tests.devWikiTest.staticMethod2();
crafttweaker.tests.devWikiTest.staticMethodVarArg(10);
crafttweaker.tests.devWikiTest.staticMethodVarArg(10,20,30,40);

print(instance.getValue());
instance.print();
instance.printWithVarArg(10);
instance.printWithVarArg(10,20,30,40);
```
