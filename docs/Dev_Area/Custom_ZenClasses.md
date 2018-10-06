# Zen 类型

我把这些放在这里，所以那些想用 ZenScript 使用它们的人可以找到。---作者

Zen 类型是一个典型的 Java 类型，但你也可以用 ZenScript 来定义。
如果你觉得 “这一点都不脚本语言” 那么你说对了.  
这就是为什么只有那些能够搞乱它的人应该找到这个。

## 关键字

这些是可以在类的主体中找到的关键字，它们将进行一些操作，例如向类添加成员。

| 关键字         | 描述                                                                                 |
| -------------- | ------------------------------------------------------------------------------------ |
| zenClass       | 定义一个新类，应后接一个类名。                                                       |
| var/val        | 定义一个字段。使用 val 来表示一个 final 字段。                                       |
| static         | 定义一个静态字段，应非空。                                                           |
| zenConstructor | 定义类构造器。                                                                       |
| function       | 定义一个方法。注意你不能定义静态方法，因为你可以在类外部来这样做。                   |
| this           | 访问当前实例，只可以在类构造器和方法中使用。例如一个参数和字段发生了冲突时访问字段。 |

## 实例

一个带注释的例子:

```
//创建一个叫做 'name' 的类，你也可以用 scripts.scriptPath.name 来访问这个类


zenClass name {

	//每个字段都需要指定类型
	//变量不需要被初始化。初始化方法与 Java 相同。


	//静态字段在 <clinit> 中初始化，也就是当类型第一次被定义的时候。
	static myStatic as string = "value";
	static otherStatic as string = "value";

	//如果字段有初始值，它们将会在构造器被调用之前初始化。
	val nonStatic as string = "123";

	//如果字段没有初始值，你可以在构造器中初始化，即使它们是 final 的。
	val nonStaticTwo as string;


	//构造器需要所有参数都指定一个类型。
	zenConstructor(parameter as string, parameter2 as string) {
		print("TETETE");
		print(parameter);


		nonStaticTwo = parameter2;
	}


	//你可以有不同的构造器，但你不能在构造器中访问其他构造器。
	zenConstructor(parameter as string) {
		print("FFFFFF");
	}


	//推荐将方法返回值的类型也进行指定。
	function myMethod(arg as string, arg1 as string) as string {
		return "value" + arg ~ arg1;
	}

}



//通过调用类名来调用构造器
var test = name("NOPE");
test = name("nope", "noper");
print(test.myMethod("one", "two"));

print("");

//你也可以通过类名来访问静态字段
print(name.myStatic);
print(name("parameter1", "parameter2").nonStatic);

val ttt = name("t");

//也可以通过实例来访问静态字段
ttt.myStatic = "1";
print(ttt.myStatic);
```
