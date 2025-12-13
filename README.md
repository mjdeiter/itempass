ItemPass for Project Lazarus EMU
A controller-based automated item-passing system for MacroQuest Next (EMU Build) + E3Next
ItemPass.lua is an advanced, fully EMU-compatible automation script that safely handles controlled item passing within a group—perfect for clickies, buff items, or rotation-based item usage.
Designed specifically for the Project Lazarus EverQuest EMU server using MacroQuest Next (MQNext) and E3Next.

Features
Automated Item Passing

Controller toon starts with the item
Sends item to each group member in sequential order
Member automatically uses the item
Member returns the item to controller
Continues until all selected members have completed their turn

Hidden Items System

Hide unwanted items (such as "No Trade" false positives)
Hidden items never appear in inventory lists or autocomplete
Manage hidden items using simple UI buttons
Stored persistently in itempass_hidden.txt

Autocomplete Item Selection
Type an item name to receive real-time suggestions from:

Saved items
Scanned inventory (with hidden items filtered out)

Profile Support
Save complete chain configurations including:

Active item
Enabled/disabled members
Chain start position
Member order

Profiles are saved to itempass_profiles.txt
Controller-Based Architecture

Runs ONLY on the controller toon
Other members respond via /e3bct through E3Next
No additional scripts needed on non-controller characters

Full ImGui UI
Comprehensive interface with panels for:

Item selection with autocomplete
Saved items management
Hidden items management
Chain member configuration
Chain preview and visualization
Real-time status logs
Profile saving and loading


Installation
1. Download ItemPass.lua
Place the file into your MQNext Lua folder:
<Your MQ Root>/Lua/ItemPass.lua
Example path:
C:\Games\Project_Lazarus\MQNext\Lua\ItemPass.lua
2. Requirements

MacroQuest Next (EMU Build)
E3Next (Project Lazarus version)


Usage
Running the Script
Open MacroQuest and execute:
/lua run itempass
This opens the full ImGui UI.
Optional Commands
/itempassui       -- Toggle UI visibility
/itempassstart    -- Start chain
/itempasspause    -- Pause chain
/itempassreset    -- Reset chain

How ItemPass Works
Controller Setup
Run the script on ONE character only (the controller). This character:

Holds the item at start
Sends trade instructions
Commands members to use the item
Requests the item back
Tracks rotation order
Handles timing, delays, failures, and zone changes

Group Member Behavior
Other group members require no additional setup. E3Next automatically handles /giveme and /useitem responses.

Chain Flow Example
Controller: Alektra
Rotation Members: Alektra → Dahma → Gimok → Shablagu → Ninadinya → Zerayn → Alektra
Execution Flow:

Alektra → Dahma

Alektra trades the item to Dahma
Script sends /e3bct Dahma /useitem "<item>"
Dahma uses the item
Dahma returns the item to Alektra


Alektra → Gimok

Gimok uses the item
Gimok returns the item to Alektra


Alektra → Shablagu

Shablagu uses the item
Shablagu returns the item to Alektra


Alektra → Ninadinya

Ninadinya uses the item
Ninadinya returns the item to Alektra


Alektra → Zerayn

Zerayn uses the item
Zerayn returns the item to Alektra


Chain Complete

Chain ends (or restarts at Dahma if AUTO_REPEAT_CHAIN = true)




Configuration Files
Generated automatically in the MQNext directory:
FilePurposeitempass_items.txtSaved item namesitempass_profiles.txtChain profilesitempass_hidden.txtHidden item list

Troubleshooting
Item not detected?

Click "Scan Inventory" button
Ensure item isn't hidden
Verify item name matches exactly

Group member not appearing?

Click "Refresh Group" button
Ensure member is in your group
Missing members are automatically disabled

Trade stuck?

ItemPass automatically retries up to 3 times
If trade fails repeatedly, chain resets safely


Credits
Originally created by Alektra <Lederhosen>

Support development: https://buymeacoffee.com/shablagu

Contributing
Contributions, forks, and feature upgrades are welcome!
Areas for enhancement:

Additional UI features
Alternate chain behaviors
Logging improvements
Visual enhancements
Remote communication improvements

Feel free to fork and submit pull requests.
