# Zen 成员和属性

Zen 成员可以使用 `object.member` 来调用。
成员可以只读，只写，或二者皆可。

## Getter 和 Setter

一共有两种 Getter：ZenGetter 和 ZenMemberGetter。
那么它们的区别在哪里呢？

正常来说你可以使用 `@ZenGetter(value)`，除非你遇到了不同成员名称的调用且返回类型相同，或你不知道调用成员名称的情况。

在这种情况下你可以使用 `@ZenMemberGetter`。
所以区别在哪里？

-   一个注解了 `@ZenGetter(value)` 的函数不需要任何参数，但 `@ZenMemberGetter` 需要一个表示 **调用成员名称** 的参数。
-   MemberGetter 函数在没有其它 Getter 函数找到的时候才执行。
-   如果你只需要调用一个简单的属性，你应该使用 `@ZenGetter(value)`。

**译者注：如 OreDictionary 中有 ingotIron，stickWood 等，你不可能每一个都用一个 @ZenGetter 注解。这种情况下 ZenMemberGetter 可以获得调用的成员名称来方便处理。**

**如下面例子的 IOreDict 中，有一个 `get` 函数，当调用 `oredict.ingotIron` 的时候就会将 `ingotIron` 传入这个函数。**

_可以类比 JavaScript 中的 `__defineGetter__`_

同样也适用于 ZenSetter 和 ZenMemberSetter。

## Zen 属性

`@ZenProperty` 组合了 `@ZenGetter(value)` 和 `@ZenSetter` 的功能。  
这个注解只能在公共字段中使用 （如 `public String name`）。

注解有以下可用参数：

-   `String value`: 属性名称（在 ZS 中使用 object.name 调用），默认为字段的名称
-   `String getter`: Getter 方法名称（可以不使用 ZenGetter 注解）
    -   如果没有设置或设置为了 `""`，默认会注册
        -   `get + value` 如果该字段不是一个 boolean 或 Boolean 值
        -   `is + value` 如果该字段是一个 boolean 或 Boolean 值
    -   如果设置为了 `null`，将不会注册一个 Getter
-   `String setter`: Setter 方法名称 （可以不使用 ZenSetter 注解）
    -   如果没有设置或设置为了 `""`，默认会注册 `set + value`
    -   如果设置为了 `null`，将不会注册一个 Setter

使用了 ZenProperty 的话你甚至可以省略 Getter 和 Setter 的代码。如果你使用了这些方法，你仍然需要添加 `@ZenMethod` 来让它们正常工作，否则将会使用自动生成的版本。

## 例子

### ZenGetters 的例子

[CraftTweaker 中的 IOreDict](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/oredict/IOreDict.java)

```
@ZenClass("crafttweaker.oredict.IOreDict")
@IterableSimple("crafttweaker.oredict.IOreDictEntry")
@ZenRegister
public interface IOreDict extends Iterable<IOreDictEntry> {


    @ZenMemberGetter
    @ZenOperator(OperatorType.INDEXGET)
    @ZenMethod
    IOreDictEntry get(String name);

    @ZenGetter("entries")
    List<IOreDictEntry> getEntries();

    @ZenOperator(OperatorType.CONTAINS)
    @ZenMethod
    boolean contains(String name);
}
```

### ZenProperty 的例子

[ContentTweaker 中的 MCAxisAlignedBB](https://github.com/The-Acronym-Coders/ContentTweaker/blob/develop/1.12/src/main/java/com/teamacronymcoders/contenttweaker/api/ctobjects/aabb/MCAxisAlignedBB.java)

```
@ZenRegister
@ZenClass("mods.contenttweaker.AxisAlignedBB")
public class MCAxisAlignedBB implements ICTObject<AxisAlignedBB> {
    @ZenProperty
    public double minX = 0.0;

    ...

    @ZenMethod
    public double getMinX() {
        return minX;
    }

    @ZenMethod
    public void setMinX(double minX) {
        this.minX = minX;
    }

    ...

}
```
