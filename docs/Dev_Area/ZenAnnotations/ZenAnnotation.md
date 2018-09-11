# Zen 注解

Zen 注解可以使 Java 中的内容暴露到 ZenScript 中并被使用。

## 类型注解

这些注解可以用于类型。

| 注解                                                                     | 值                                                                   | 应用目标 | 提示                                                                           |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------------ |
| [`@ZenClass`](/Dev_Area/ZenAnnotations/Annotation_ZenClass/)             | Zen 类型名称 (如 `crafttweaker.item.IItemStack`)，可以和方法名称不同 | Class    | 名称必须唯一                                                                   |
| [`@ZenExpansion`](/Dev_Area/ZenAnnotations/Annotation_ZenExpansion/)     | 扩展一个 Zen 类 (如 `crafttweaker.item.IItemStack`)                  | Class    | 类名必须存在（你不能扩展一个不存在的类）                                       |
| [`@ZenRegister`](/Dev_Area/ZenAnnotations/Annotation_ZenRegister/)       |                                                                      | Class    | 用于自动注册类或扩展类                                                         |
| [`@IterableList`](/Dev_Area/ZenAnnotations/Annotation_Iterable/)         | 列表类型名称 (如 `crafttweaker.mods.IMod`)                           | Class    | 类型必须实现 `List<Type>`                                                      |
| [`@IterableMap`](/Dev_Area/ZenAnnotations/Annotation_Iterable/)          | 键-值类型名称 (如 `string`, `crafttweaker.item.IItemStack`)          | Class    | 类型必须实现 `Map<KeyType, ValueType>`                                         |
| [`@IterableSimple`](/Dev_Area/ZenAnnotations/Annotation_Iterable/)       | 可迭代类型名称 (如 `crafttweaker.mods.IMod`)                         | Class    | 类型必须实现 `Iterable<Type>`                                                  |
| [`@BracketHandler`](/Dev_Area/ZenAnnotations/Annotation_BracketHandler/) | 尖括号处理器及优先度 (如 `priority = 19`)                            | Class    | 类型必须实现 `IBracketHandler`                                                 |
| [`@ModOnly`](/Dev_Area/ZenAnnotations/Annotation_ModOnly/)               | 前置模组名称 (`isModLoaded(annotation.getValue())` 需要为 true)      | Class    | 与 [`@ZenRegister`](/Dev_Area/ZenAnnotations/Annotation_ZenRegister/) 组合使用 |

## 参数注解

这些注解可以用于方法参数。

| 注解                                                         | 应用目标  | 信息                                 |
| ------------------------------------------------------------ | --------- | ------------------------------------ |
| `@NotNull`                                                   | Parameter | 尚未实现                             |
| [`@Optional`](/Dev_Area/ZenAnnotations/Annotation_Optional/) | Parameter | 将参数表示为可选，调用函数时可以省略 |

## 方法注解

这些注解可以用于方法。

| 注解                                                                       | 值                                    | 应用目标 |
| -------------------------------------------------------------------------- | ------------------------------------- | -------- |
| [`@ZenCaster`](/Dev_Area/ZenAnnotations/Annotation_ZenCaster/)             |                                       | Method   |
| [`@ZenOperator`](/Dev_Area/ZenAnnotations/Annotation_ZenOperator/)         | [Zen 操作符](/Dev_Area/ZenOperators/) | Method   |
| [`@ZenGetter`](/Dev_Area/ZenAnnotations/ZenMembers/)                       | getter 名称，调用时可省略()           | Method   |
| [`@ZenSetter`](/Dev_Area/ZenAnnotations/ZenMembers/)                       | setter 名称，调用时可省略()           | Method   |
| [`@ZenMemberGetter`](/Dev_Area/ZenAnnotations/ZenMembers/)                 |                                       | Method   |
| [`@ZenMemberSetter`](/Dev_Area/ZenAnnotations/ZenMembers/)                 |                                       | Method   |
| [`@ZenMethod`](/Dev_Area/ZenAnnotations/Annotation_ZenMethod/)             |                                       | Method   |
| [`@ZenMethodStatic`](/Dev_Area/ZenAnnotations/Annotation_ZenMethodStatic/) |                                       | Method   |
| [`@ZenDoc`](/Dev_Area/ZenAnnotations/Annotation_ZenDoc/)                   | `dumpZS` 中的额外信息                 | Method   |

## 字段注解

这些注解可以应用于 public 字段。

| 注解                                                   | 应用目标 | 信息                                       |
| ------------------------------------------------------ | -------- | ------------------------------------------ |
| [`@ZenProperty`](/Dev_Area/ZenAnnotations/ZenMembers/) | Field    | 组合了 `@ZenSetter` 和 `@ZenGetter` 的行为 |
