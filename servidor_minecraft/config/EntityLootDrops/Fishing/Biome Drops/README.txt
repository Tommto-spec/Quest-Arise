Biome-Specific Fishing Drops
===========================

This directory contains fishing drops that only trigger in specific biomes.
Each file can contain drops for one or multiple related biomes.

Common Fishing Biomes:
--------------------
Ocean Biomes:
- minecraft:ocean
- minecraft:deep_ocean
- minecraft:warm_ocean
- minecraft:lukewarm_ocean
- minecraft:cold_ocean
- minecraft:frozen_ocean
- minecraft:deep_warm_ocean
- minecraft:deep_lukewarm_ocean
- minecraft:deep_cold_ocean
- minecraft:deep_frozen_ocean

River Biomes:
- minecraft:river
- minecraft:frozen_river

Swamp Biomes:
- minecraft:swamp
- minecraft:mangrove_swamp

Other Water Biomes:
- minecraft:beach
- minecraft:stony_shore
- minecraft:mushroom_fields

Suggested File Organization:
-------------------------
- Ocean_Drops.json - All ocean biome drops
- River_Drops.json - River and stream drops
- Swamp_Drops.json - Swamp-specific drops
- Cold_Water_Drops.json - Frozen/cold biome drops
- Warm_Water_Drops.json - Tropical biome drops

Example Biome Drop Configuration:
--------------------------------
```json
[
  {
    "name": "ocean_treasure",
    "biome": "minecraft:deep_ocean",
    "chance": 0.05,
    "rewards": [
      {
        "item": "minecraft:prismarine_shard",
        "minCount": 1,
        "maxCount": 3,
        "chance": 0.7
      },
      {
        "item": "minecraft:heart_of_the_sea",
        "count": 1,
        "chance": 0.01
      }
    ],
    "commands": [
      "tellraw {player} {\"text\":\"The deep ocean yields its treasures...\",\"color\":\"aqua\"}"
    ]
  }
]
```

Tips for Biome-Specific Drops:
-----------------------------
1. Match drops to biome themes (coral in warm oceans, ice in frozen biomes)
2. Use different rarities for different biomes
3. Consider combining biome conditions with weather/time conditions
4. Deep ocean biomes can have rarer drops than regular oceans
5. Rivers might have different drops than oceans
6. Swamps could have unique magical or mysterious drops
7. Test biome detection in-game to ensure drops trigger correctly

Biome Detection:
---------------
The system detects the biome where the fishing bobber lands, not where the player stands.
This allows for fishing across biome boundaries with appropriate drops.
