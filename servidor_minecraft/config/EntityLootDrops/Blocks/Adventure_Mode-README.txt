# Adventure Mode Block Restrictions

This is Disabled by default.

## Overview

Adventure Mode allows you to restrict which blocks players can break, place, or modify in specific dimensions.
These restrictions only apply to players in Survival or Adventure mode. Players in Creative mode are not affected.

## How It Works

- Each entry in the JSON file defines rules for a specific dimension.
- Only blocks listed in `allowedBlockBreakIDs` can be broken if the rule is enabled.
- Only blocks listed in `allowedPlacementIDs` can be placed if `preventBlockPlacement` is true.
- Only blocks listed in `allowedModificationIDs` can be modified (e.g., right-clicked) if `preventBlockModification` is true.
- Use `tag:namespace:tagname` to allow all blocks in a tag (e.g., `tag:minecraft:logs`).
- Each rule can be enabled/disabled and set for a specific dimension.
- Players in Creative mode are not restricted.
- Custom messages can be shown when a player is prevented from breaking, placing, or modifying a block.

## Example JSON Entry

```
[
  {
    "enabled": true,
    "dimension": "minecraft:overworld",
    "allowedBlockBreakIDs": [
      "minecraft:oak_log",
      "minecraft:coal_ore",
      "tag:forge:ores",
      "tag:minecraft:logs",
      "minecraft:stone"
    ],
    "preventBlockPlacement": true,
    "allowedPlacementIDs": [
      "minecraft:torch",
      "minecraft:ladder",
      "tag:minecraft:signs",
      "tag:minecraft:beds"
    ],
    "preventBlockModification": true,
    "allowedModificationIDs": [
      "minecraft:dirt",
      "minecraft:grass_block",
      "tag:minecraft:logs"
    ],
    "breakMessage": "This block is protected and cannot be broken!",
    "placeMessage": "You cannot place blocks here!",
    "modifyMessage": "You cannot modify blocks here!"
  }
]
```

## Regenerating Blocks

You can make any block automatically regenerate after being broken by configuring it in the `Blocks/Normal Drops` folder.
To do this, open or create a JSON file for the block you want to regenerate (for example, `Blocks/Normal Drops/stone_drops.json`).

Add or edit a drop entry to include the following properties:

- `"canRegenerate": true` — Enables regeneration for this block.
- `"brokenBlockReplace": "minecraft:bedrock"` — The block to temporarily replace the broken block with (e.g., bedrock, barrier, or air).
- `"respawnTime": 20` — Time in seconds before the original block is restored.

### Example Regenerating Block Entry
```json
{
  "blockId": "minecraft:stone",
  "itemId": "minecraft:diamond",
  "dropChance": 100.0,
  "minAmount": 1,
  "maxAmount": 1,
  "canRegenerate": true,
  "brokenBlockReplace": "minecraft:bedrock",
  "respawnTime": 20
}
```

You can add these properties to any block drop entry in the `Blocks/Normal Drops` folder. When a player breaks the block, it will be replaced with the specified block (e.g., bedrock) and then automatically restored after the given time.
This system is separate from Adventure Mode and works for any block you configure.

---
For further help, see the main README or ask on the mod's support channels.
