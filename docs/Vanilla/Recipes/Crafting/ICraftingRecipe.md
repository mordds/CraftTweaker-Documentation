# 合成配方

ICraftingRecipe 是 Zenscript 所看到的工作台配方。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.recipes.ICraftingRecipe`

## ZenMethods/Getters

### 获取配料

返回一个一维的 [IIngredient](/Vanilla/Variable_Types/IIngredient)[] 或二维的 [IIngredient](/Vanilla/Variable_Types/IIngredient)[][]。

```
rec.ingredients1D
rec.ingredients2D
```

### 获取标准输出

获取一个 [IItemStack](/Vanilla/Items/IItemStack) 类型的标准输出，可能为 null。

```
rec.output
```

### 检查条件

下列的每一个字段都是一个 boolean

```
rec.hasTransformers;
rec.hasRecipeAction;
rec.hasRecipeFunction;
rec.hidden;
rec.shaped;
```

### 域

一般来说是提供该合成的 modid。

```
rec.resourceDomain;
rec.fullResourceDomain;
```

### 转为 String

```
rec.commandString;
rec.toCommandString();

rec.name;
rec.getName();
```
