# 合成原材料

CraftTweaker 引入了 [IIngredient](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/item/IIngredient.java) 作为原材料接口。
继承了这个接口的接口列表：

- [IItemStack](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/item/IItemStack.java)
- [ILiquidStack](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/liquid/ILiquidStack.java)
- [IOreDictEntry](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-API/src/main/java/crafttweaker/api/oredict/IOreDictEntry.java)

## 选择哪一个

推荐的来说，你应该使用 IIngredient。为什么？
因为大量用户期待一个接受 IItemStack 的方法也同样接受一个 IOreDictEntry，这就是原因。
同时，也有那些需要返回 IIngredient 的方法，例如 IngredientConditions (`<mincraft:grass>.onlyDamaged()` 或 `iron_ingot | gold_ingot`).

## 如何从一个 IIngredient 获得物品/流体？

有很多方法来获得你需要的类型：  
你可以使用 `ingredient.getItems()` 来获得一个包括所有匹配的物品的 `List<IItemStack>`。这也同时意味着这个物品如果有判断条件，它们将会被丢弃。
对于流体来说，你可以使用 `ingredients.getFluids()` 来获得一个包括所有匹配的流体的 `List<ILiquidStack>`。同样，这也意味着这个流体如果有判断条件，它们将会被丢弃。

## 如何得到原版的 ItemStack/FluidStack？

你可以使用 [CraftTweakerMC](https://github.com/jaredlll08/CraftTweaker/blob/1.12/CraftTweaker2-MC1120-Main/src/main/java/crafttweaker/api/minecraft/CraftTweakerMC.java).  
如果你依赖了 MTLib，你可以使用它的替代方法 [input helper](https://github.com/jaredlll08/MTLib/blob/1.12/src/main/java/com/blamejared/mtlib/helpers/InputHelper.java).  
如果你依赖 ItemConditions 的方法，你应该使用 `ingredient.matches(IItemStack other)`。
