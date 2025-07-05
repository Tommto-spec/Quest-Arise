Event Drops Configuration
========================

This directory contains drops that only activate during specific events.

Built-in Events:
- Winter/: Winter-themed drops
- Summer/: Summer-themed drops
- Easter/: Easter-themed drops
- Halloween/: Halloween-themed drops

Custom Events:
You can create your own event folders with any name.
Each event folder should contain:
- Global_Hostile_Drops.json: Event-specific hostile drops
- Mobs/: Event-specific entity drops

Event Management:
- /lootdrops event <eventName> true - Enable event
- /lootdrops event <eventName> false - Disable event
- /lootdrops active_events - List active events
- /lootdrops listall - List all available events
