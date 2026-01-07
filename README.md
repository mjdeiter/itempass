# ItemPass

**Originally created by Alektra <Lederhosen>**

[![Buy Me a Coffee](https://img.shields.io/badge/Support-Buy%20Me%20a%20Coffee-ffdd00?logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/shablagu)

ItemPass is a deterministic, EMU-safe item circulation tool for the  
**Project Lazarus EverQuest EMU server**, built for **MacroQuest MQNext (MQ2Mono)** and **E3Next**.

It allows a controller character to pass an item through a configurable group
chain so each member can click/use it in sequence.

<img width="763" height="894" alt="image" src="https://github.com/user-attachments/assets/831f333f-6f19-40e6-9249-240974df375a" />


---

## Features

### Core Functionality
- Deterministic item pass chain execution
- EMU-safe inventory scanning (no `FindItem`)
- Works with bags and stacked items
- Robust FSM-based execution (no timing guesswork)

### Controller-Aware Design (v1.1.3)
- Controller is **never included in trade chains**
- Optional controller participation via **local end-of-chain click**
- Prevents self-trade and NULL `/giveme` edge cases
- Explicit FSM phase for controller-only actions

### Chain Management
- Per-member enable/disable checkboxes
- `(Start)` marker to control chain order
- Live chain preview
- Manual start, pause, and reset controls

### Profiles
- Save and load full chain + item configurations
- Profiles persist item name, chain order, and enabled members
- Safe auto-healing if group composition changes

### UI
- ImGui-based interface
- Inventory scan with autocomplete
- Hidden-item support (filter junk permanently)
- Persistent status log with timestamps

---

## Requirements

- Project Lazarus EverQuest EMU
- MacroQuest **MQNext (MQ2Mono)**
- E3Next (for `/giveme` and remote `/useitem`)
- ImGui enabled

---

## Installation

1. Copy `itempass.lua` into your MacroQuest `lua` directory
2. In game, run:
