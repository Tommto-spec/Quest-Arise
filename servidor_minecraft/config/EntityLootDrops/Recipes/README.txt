Custom Recipes Configuration Guide
================================

This system allows you to add custom crafting recipes to the game.

Directory Structure:
-------------------
config/EntityLootDrops/Recipes/
  ├── Shaped/              # Shaped crafting recipes
  ├── Shapeless/           # Shapeless crafting recipes
  ├── Brewing/             # Brewing stand recipes
  ├── Furnace/             # Furnace/smelting recipes
  └── Smithing/            # Smithing table recipes

Recipe Types:
------------
1. Shaped: Recipes where ingredient placement matters (like vanilla crafting)
2. Shapeless: Recipes where ingredients can be placed anywhere
3. Brewing: Potion brewing recipes for brewing stands
4. Furnace: Smelting recipes for furnaces and similar blocks
5. Smithing: Upgrade recipes for smithing tables

For detailed configuration instructions, see the README files in each subdirectory.

Commands:
--------
/recipes reload - Reload recipe configuration
/recipes list - List all custom recipes
/recipes give <player> <recipeId> - Give a recipe to a player
