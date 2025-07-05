Dimension-Specific Fishing Drops
===============================

This directory contains fishing drops that only trigger in specific dimensions.
Each file can contain drops for one or multiple related dimensions.

Standard Minecraft Dimensions:
----------------------------
- minecraft:overworld - The main world
- minecraft:the_nether - The Nether dimension
- minecraft:the_end - The End dimension

Modded Dimensions:
----------------
You can also use dimensions from other mods by using their full dimension ID.
Examples might include:
- twilightforest:twilight_forest
- aether:the_aether
- undergarden:undergarden

Suggested File Organization:
-------------------------
- Overworld_Drops.json - Standard overworld fishing
- Nether_Drops.json - Nether lava fishing (if possible)
- End_Drops.json - End dimension fishing
- Modded_Dimension_Drops.json - Other mod dimensions

Example Dimension Drop Configuration:
-----------------------------------
```json
[
  {
    "name": "nether_fishing",
    "dimension": "minecraft:the_nether",
    "chance": 0.1,
    "rewards": [
      {
        "item": "minecraft:magma_cream",
        "minCount": 1,
        "maxCount": 2,
        "chance": 0.6
      },
      {
        "item": "minecraft:blaze_powder",
        "count": 1,
        "chance": 0.3
      },
      {
        "item": "minecraft:ghast_tear",
        "count": 1,
        "chance": 0.05
      }
    ],
    "commands": [
      "tellraw {player} {\"text\":\"The lava yields fiery treasures...\",\"color\":\"red\"}"
    ]
  },
  {
    "name": "end_fishing",
    "dimension": "minecraft:the_end",
    "chance": 0.08,
    "rewards": [
      {
        "item": "minecraft:ender_pearl",
        "count": 1,
        "chance": 0.5
      },
      {
        "item": "minecraft:chorus_fruit",
        "minCount": 1,
        "maxCount": 3,
        "chance": 0.4
      },
      {
        "item": "minecraft:dragon_breath",
        "count": 1,
        "chance": 0.02
      }
    ],
    "commands": [
      "tellraw {player} {\"text\":\"The void whispers secrets...\",\"color\":\"dark_purple\"}"
    ]
  }
]
```

Tips for Dimension-Specific Drops:
--------------------------------
1. Match drops to dimension themes (fire items in Nether, void items in End)
2. Consider if fishing is even possible in the dimension (Nether has lava)
3. Use higher rarity for dimension-specific materials
4. Combine with other conditions for very specific scenarios
5. Test fishing mechanics in each dimension
6. Consider dimension-specific enchantments or tools
7. Use appropriate command feedback for each dimension's atmosphere

Special Considerations:
---------------------
- Nether: Fishing in lava may require special mechanics
- End: Limited water sources, may need custom water placement
- Modded Dimensions: Check if fishing mechanics work as expected
- Dimension Detection: System detects where the fishing occurs, not player location
