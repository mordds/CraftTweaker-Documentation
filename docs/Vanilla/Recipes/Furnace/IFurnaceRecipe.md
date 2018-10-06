# 烧炼配方

ICraftingRecipe 是 Zenscript 所看到的烧炼配方。

## 导入包

如果你的脚本遇到问题，请检查是否导入了相关的包。（比如声明[数组](/AdvancedFunctions/Arrays_and_Loops)。）所以保险起见，请在一开始写脚本的时候就确保导入了可能用到的包。

`import crafttweaker.recipes.IFurnaceRecipe`

## ZenMethods/Getters

### 转为 String

```
rec.commandString;
rec.toCommandString();
```

### 其他 Getter

```
rec.input; // 输入
rec.output; // 输出
rec.xp; // 经验值
```
