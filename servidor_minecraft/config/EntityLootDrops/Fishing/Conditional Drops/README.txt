Conditional Fishing Drops
========================

This directory contains fishing drops that trigger based on specific conditions
like weather, time of day, enchantments, or player level.

Supported Conditions:
-------------------
- weather: "clear", "rain", "thunder"
- timeOfDay: "day", "night"
- minFishingLevel: Minimum player experience level
- requiresLure: Requires Lure enchantment on fishing rod
- requiresLuckOfSea: Requires Luck of the Sea enchantment

Example Conditions:
-----------------
1. Night fishing with special rewards
2. Rain fishing for oceanic items
3. Thunder storms for rare catches
4. High-level fishing for exclusive rewards
5. Enchanted rod requirements for magical catches

File Format:
-----------
Each JSON file should contain an array of fishing drop objects.
You can create multiple files to organize different types of conditions.

Suggested File Names:
-------------------
- Weather_Time_Drops.json
- Enchantment_Drops.json
- Level_Gated_Drops.json
- Special_Conditions.json
