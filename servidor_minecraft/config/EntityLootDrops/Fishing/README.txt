Fishing Drops Configuration Guide
===============================

The fishing drops system allows you to create custom rewards and execute commands when players fish.
This system uses a folder structure with separate JSON files for different types of drops.

Directory Structure:
-------------------
config/EntityLootDrops/Fishing/
  ├── Global_Fishing_Rewards.json    # Global rewards for any fishing
  ├── Conditional Drops/             # Weather/time-based drops
  ├── Biome Drops/                   # Biome-specific drops
  └── Dimension Drops/               # Dimension-specific drops

File Types:
----------
1. Global_Fishing_Rewards.json: Simple rewards that can trigger on any fishing event
2. Conditional Drops: Drops with weather, time, or enchantment requirements
3. Biome Drops: Drops specific to certain biomes (ocean, river, etc.)
4. Dimension Drops: Drops specific to dimensions (overworld, nether, end)

Configuration Format:
--------------------
All fishing drop files use JSON arrays containing drop objects.

Fishing Drop Properties:
----------------------
Required Properties:
- name: Unique identifier for the fishing drop
- chance: Probability to trigger (0.0 to 1.0, where 1.0 = 100%)

Optional Condition Properties:
- biome: Required biome (e.g., "minecraft:ocean", "minecraft:river")
- dimension: Required dimension (e.g., "minecraft:overworld", "minecraft:nether")
- weather: Required weather ("clear", "rain", "thunder")
- timeOfDay: Required time ("day", "night")
- minFishingLevel: Minimum player experience level required
- requiresLure: Whether Lure enchantment is required (true/false)
- requiresLuckOfSea: Whether Luck of the Sea enchantment is required (true/false)

Reward Properties:
- rewards: Array of items to give when the drop triggers
- commands: Array of commands to execute when the drop triggers

Fishing Reward Properties:
------------------------
- item: Item ID to give (e.g., "minecraft:diamond")
- count: Fixed amount to give (use this OR min/maxCount)
- minCount: Minimum amount to give (random between min and max)
- maxCount: Maximum amount to give (random between min and max)
- chance: Probability for this specific reward (0.0 to 1.0)
- nbt: Optional NBT data for the item

Command Placeholders:
-------------------
You can use these placeholders in commands:
- {player}: Player's name
- {uuid}: Player's UUID
- {x}: Player's X coordinate
- {y}: Player's Y coordinate
- {z}: Player's Z coordinate

Example Global Fishing Rewards:
------------------------------
```json
[
  {
    "item": "minecraft:experience_bottle",
    "count": 1,
    "chance": 0.1
  },
  {
    "item": "minecraft:emerald",
    "minCount": 1,
    "maxCount": 2,
    "chance": 0.05
  }
]
```

Example Conditional Drop:
-----------------------
```json
[
  {
    "name": "night_fishing_bonus",
    "timeOfDay": "night",
    "chance": 0.15,
    "rewards": [
      {
        "item": "minecraft:glowstone_dust",
        "minCount": 1,
        "maxCount": 3,
        "chance": 0.8
      }
    ],
    "commands": [
      "tellraw {player} {\"text\":\"The night brings mysterious catches...\",\"color\":\"dark_purple\"}"
    ]
  }
]
```

UNDERSTANDING 'GLOBAL' FILES:
============================
Files with 'Global' in the name apply to ALL fishing scenarios unless
you have more specific configurations in other folders.

HOW TO DISABLE FISHING DROPS:
=============================
To disable fishing drops without deleting files:

Method 1 - Empty Array (Disables ALL drops in file):
Replace the entire file content with: []

Method 2 - Set Chance to 0 (Disables specific drops):
Set "chance": 0 for drops you want to disable
(Note: Fishing drops don't use commandChance, commands are part of the drop configuration)

Example - Completely Disabled File:
```json
[]
```

Example - Selectively Disabled Drops:
```json
[
  {
    "name": "rare_catch",
    "chance": 0,
    "rewards": [
      {
        "item": "minecraft:diamond",
        "count": 1,
        "chance": 1.0
      }
    ]
  }
]
```
(This disables the entire drop group by setting main chance to 0)

Tips:
----
1. Use low chance values (0.01-0.1) for rare drops to maintain balance
2. Combine multiple conditions to create very specific scenarios
3. Global fishing rewards are good for common bonuses
4. Test your NBT data in-game before adding to config
5. Use commands to provide feedback to players about special catches
6. Consider using minFishingLevel to gate powerful rewards
7. Organize drops by type using the different folders

Commands:
--------
(Note: These commands would need to be implemented in a FishingCommand class)
/fishingdrops reload - Reload fishing configuration
/fishingdrops list - List all configured fishing drops
/fishingdrops test <dropName> - Test a specific fishing drop

For detailed information about each drop type, see the README files in the subdirectories.
