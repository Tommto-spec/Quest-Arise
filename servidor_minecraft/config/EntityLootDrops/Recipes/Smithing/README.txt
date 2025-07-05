Smithing Recipes Configuration
============================

Smithing recipes allow you to create custom upgrade combinations
for smithing tables, similar to netherite upgrades.

Configuration Format:
-------------------
```json
{
  "recipeId": "custom:enhanced_diamond_sword",
  "template": "minecraft:netherite_upgrade_smithing_template",
  "base": "minecraft:diamond_sword",
  "addition": "minecraft:emerald",
  "result": {
    "item": "minecraft:diamond_sword",
    "count": 1,
    "nbt": "{display:{Name:'\"Enhanced Diamond Sword\"},Enchantments:[{id:\"minecraft:sharpness\",lvl:6}]}"
  },
  "copyNbt": true,
  "copyEnchantments": true,
  "command": "tellraw @a {\"text\":\"Someone created an enhanced weapon!\"}",
  "commandChance": 1.0
}
```

Properties:
----------
- recipeId: Unique identifier for the recipe
- template: Smithing template required (1.20+ feature)
- base: The base item to be upgraded
- addition: The upgrade material
- result: The resulting upgraded item
- copyNbt: Whether to copy NBT data from base item
- copyEnchantments: Whether to copy enchantments from base item
- command: Optional command to execute when smithed
- commandChance: Probability to execute command (0.0-1.0)

Smithing Templates (1.20+):
-------------------------
- minecraft:netherite_upgrade_smithing_template
- minecraft:armor_trim_smithing_template
- minecraft:coast_armor_trim_smithing_template
- minecraft:dune_armor_trim_smithing_template
- minecraft:eye_armor_trim_smithing_template
- minecraft:host_armor_trim_smithing_template
- minecraft:raiser_armor_trim_smithing_template
- minecraft:rib_armor_trim_smithing_template
- minecraft:sentry_armor_trim_smithing_template
- minecraft:shaper_armor_trim_smithing_template
- minecraft:silence_armor_trim_smithing_template
- minecraft:snout_armor_trim_smithing_template
- minecraft:spire_armor_trim_smithing_template
- minecraft:tide_armor_trim_smithing_template
- minecraft:vex_armor_trim_smithing_template
- minecraft:ward_armor_trim_smithing_template
- minecraft:wayfinder_armor_trim_smithing_template
- minecraft:wild_armor_trim_smithing_template

Legacy Format (Pre-1.20):
------------------------
For versions before 1.20, omit the template field:
```json
{
  "recipeId": "custom:legacy_upgrade",
  "base": "minecraft:iron_sword",
  "addition": "minecraft:diamond",
  "result": {
    "item": "minecraft:diamond_sword",
    "count": 1
  }
}
```

Common Upgrade Materials:
-----------------------
- minecraft:netherite_ingot - Netherite upgrades
- minecraft:diamond - Diamond upgrades
- minecraft:emerald - Emerald enhancements
- minecraft:gold_ingot - Gold plating
- minecraft:iron_ingot - Iron reinforcement
- Custom items - Your mod's upgrade materials

NBT and Enchantment Copying:
---------------------------
- copyNbt: true - Preserves custom names, lore, and other NBT data
- copyEnchantments: true - Preserves all enchantments from base item
- Both can be combined with additional NBT in the result
- Result NBT will be merged with copied NBT

Tips:
----
1. Use appropriate templates for the upgrade type
2. Consider preserving enchantments and NBT for upgrades
3. Test NBT merging behavior in-game
4. Balance upgrade costs with the benefits provided
5. Use commands to announce significant upgrades
6. Consider creating upgrade chains (iron → diamond → custom)
7. Armor trims require specific templates and materials
