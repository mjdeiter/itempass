[![Support](https://img.shields.io/badge/Support-Buy%20Me%20a%20Coffee-6f4e37)](https://buymeacoffee.com/shablagu)

# ItemPass (Project Lazarus)

A controller-based automated item-passing system for Project Lazarus EverQuest EMU, built for MacroQuest MQNext (EMU build) with E3Next integration.

---

## Credits
**Created by:** Alektra  
**For:** Project Lazarus EverQuest EMU Server  

---

## Description
ItemPass is an advanced, fully EMU-compatible automation script designed to safely manage controlled item passing within a group.

It is ideal for clickies, buff items, and rotation-based item usage where a single item must be shared among multiple group members in a predictable and reliable order.

The script is **controller-driven**, runs on only one character, and leverages E3Next for all group member interaction—requiring no additional scripts on non-controller toons.

---

## Key Features

### Automated Item Passing
- Controller starts with the item
- Item is passed to each selected group member in sequence
- Member automatically uses the item
- Item is returned to the controller
- Continues until all configured members complete their turn

### Hidden Items System
- Hide unwanted or misleading items (e.g., No Trade false positives)
- Hidden items never appear in inventory lists or autocomplete
- Manage hidden items through the UI
- Persisted to `itempass_hidden.txt`

### Autocomplete Item Selection
Type an item name to receive real-time suggestions from:
- Saved items
- Scanned inventory (hidden items excluded)

### Profile Support
Save and load complete chain configurations, including:
- Active item
- Enabled / disabled members
- Chain start position
- Member order

Profiles are stored in `itempass_profiles.txt`.

### Controller-Based Architecture
- Runs **only** on the controller toon
- Other members respond via `/e3bct` through E3Next
- No automation or polling on non-controller characters

### Full ImGui Interface
Comprehensive UI providing:
- Item selection with autocomplete
- Saved items management
- Hidden items management
- Chain member configuration
- Chain preview and visualization
- Real-time status and logs
- Profile saving and loading

---

## Requirements
- Project Lazarus EverQuest EMU server
- MacroQuest MQNext (EMU build)
- E3Next (Lazarus-compatible)

---

## Installation
1. Download `ItemPass.lua`.
2. Place the file in your MQNext Lua directory:
