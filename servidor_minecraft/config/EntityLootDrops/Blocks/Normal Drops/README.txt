Normal Drops Configuration
========================

Configuration Format:
-------------------
Block drops use JSON format with these properties:

Basic Properties:
- blockId: The Minecraft block ID (e.g., "minecraft:stone") - only for block-specific drops
- itemId: The item to drop (e.g., "minecraft:diamond")
- dropChance: Percentage chance to drop (0-100)
- minAmount: Minimum amount to drop
- maxAmount: Maximum amount to drop
- requirePlayerBreak: If true, only drops when broken by a player
- allowDefaultDrops: If true, keeps vanilla drops

Tool Requirements:
- requiredTool: Specific tool required (e.g., "minecraft:diamond_pickaxe")
- requiredEnchantment: Required enchantment (e.g., "minecraft:fortune")
- requiredEnchantLevel: Required enchantment level

Advanced Features:
- nbtData: Custom NBT data for the dropped item
- command: Command to execute when the block breaks
- commandChance: Percentage chance to execute the command
- allowModIDs: List of mod IDs allowed to drop items when allowDefaultDrops is false

UNDERSTANDING 'GLOBAL' FILES:
============================
Files with 'Global' in the name (like Global_Block_Drops.json) apply to ALL blocks
of that type, unless you have a more specific configuration.

For example:
- Global_Block_Drops.json: Affects ALL blocks when broken
- Block Types/stone.json: Only affects stone blocks specifically
- Block Types/diamond_ore.json: Only affects diamond ore blocks

If you have both a global file and a specific block file, the specific
block file takes priority for that block type.

HOW TO DISABLE DROPS WITHOUT DELETING FILES:
==========================================
You can disable all drops in a file without deleting it using these methods:

Method 1 - Empty Array:
Replace the entire content with: []

Method 2 - Set Drop Chance and Command Chance to 0:
Set "dropChance": 0 for all drops you want to disable

Method 3 - Comment Out (Not Recommended):
JSON doesn't support comments, so use Method 1 or 2 instead

Example of Disabled File:
```json
[]
```

Example of Disabled Drop (keeping file structure):
```json
[
  {
    "blockId": "minecraft:stone",
    "itemId": "minecraft:diamond",
    "dropChance": 0,
    "commandChance": 0,
    "minAmount": 1,
    "maxAmount": 1,
    "command": "say Stone was broken!"
  }
]
```
(This disables both the diamond drop AND the command execution)

