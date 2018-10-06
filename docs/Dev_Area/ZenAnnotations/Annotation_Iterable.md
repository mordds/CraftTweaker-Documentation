# 可迭代

Iterable 注解可以让应用的类型在 ZS 中被迭代。
一共有三种注解：

-   `@IterableSimple` (需要实现 `Iterable`)
-   `@IterableList` (需要实现 `List`)
-   `@IterableMap` (需要实现 `Map`)

## 例子

[CraftTweaker 的 IOreDict](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/oredict/IOreDict.java)

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

[MCOreDict (implementation)](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-MC1120-Main/src/main/java/crafttweaker/mc1120/oredict/MCOreDict.java)

```
    @Override
    public Iterator<IOreDictEntry> iterator() {
        return Arrays.asList(OreDictionary.getOreNames())
                .stream()
                .map(CraftTweakerMC::getOreDict)
                .iterator();

    }
```

## 如何在 ZS 中使用？

```
for oreDictEntry in oreDict {
	print(oreDictEntry.name);
}
```

## 可以被注解的类型 || 附加信息

你可以注解任何实现了那些接口的类型。
你需要在注解中提供一个迭代的 [ZenScript 类型](/Dec_Area/ZenAnnotations/ZenClass/) 名称。
