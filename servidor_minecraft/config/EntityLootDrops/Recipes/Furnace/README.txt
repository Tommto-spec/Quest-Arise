Furnace Recipes Configuration
===========================

Furnace recipes allow you to create custom smelting combinations
for furnaces, blast furnaces, and smokers.

Configuration Format:
-------------------
```json
{
  "recipeId": "custom:diamond_ingot",
  "ingredient": "minecraft:diamond_ore",
  "result": {
    "item": "minecraft:diamond",
    "count": 2,
    "nbt": "{display:{Name:'\"Refined Diamond\"}}"
  },
  "experience": 1.0,
  "cookingTime": 200,
  "furnaceType": "all",
  "command": "tellraw @a {\"text\":\"Someone smelted refined diamonds!\"}",
  "commandChance": 0.05
}
```

Properties:
----------
- recipeId: Unique identifier for the recipe
- ingredient: The item to be smelted
- result: The resulting item after smelting
- experience: Experience points awarded for smelting
- cookingTime: Time in ticks to smelt (200 = 10 seconds)
- furnaceType: Which furnaces can use this recipe
- command: Optional command to execute when smelted
- commandChance: Probability to execute command (0.0-1.0)

Furnace Types:
-------------
- "all" - Works in all furnace types
- "furnace" - Only regular furnaces
- "blast_furnace" - Only blast furnaces (faster for ores/armor)
- "smoker" - Only smokers (faster for food)
- "campfire" - Only campfires (slower cooking)

Standard Cooking Times:
---------------------
- Regular Furnace: 200 ticks (10 seconds)
- Blast Furnace: 100 ticks (5 seconds) - for ores/armor
- Smoker: 100 ticks (5 seconds) - for food
- Campfire: 600 ticks (30 seconds)

Experience Values:
----------------
Common experience values for reference:
- Raw food → Cooked food: 0.1-0.35
- Raw ores → Ingots: 0.1-1.0
- Stone → Smooth stone: 0.1
- Sand → Glass: 0.1
- Custom recipes: 0.1-2.0 (balance as needed)

Tips:
----
1. Match furnace types to recipe themes (blast furnace for ores)
2. Use appropriate cooking times for balance
3. Consider fuel efficiency when setting cooking times
4. Test recipes in-game to ensure they work as expected
5. Use commands to announce rare smelting results
6. Balance experience rewards with vanilla recipes
