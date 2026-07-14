# Zoryth AI Boss v1.5 Documentation

Zoryth AI Boss is a Premium Boss Framework for Paper 1.21.x that allows you to create unlimited custom bosses from YAML configuration.

## What's New in v1.5

### 🥚 Spawn Egg CustomModelData
- `/zoryth giveegg` now sets `CustomModelData` on the spawn egg item.
- Added `cmd:` field to the `model:` section in boss YAMLs (optional, default 0).
- Example:
  ```yaml
  model:
    cmd: 1001
  ```
- Each boss YAML can be updated with a unique `cmd` value (e.g., 1001–1013) to give it a custom spawn egg texture using resource packs.

---

## 🛠️ Commands

The main command for the framework is `/zoryth` (Aliases: `/zab`, `/boss`).

| Command | Description | Permission |
|---------|-------------|------------|
| `/zoryth create` | Create a new boss definition | `zoryth.create` |
| `/zoryth delete` | Delete a boss definition | `zoryth.delete` |
| `/zoryth edit` | Edit a boss definition in-game | `zoryth.edit` |
| `/zoryth spawn` | Spawn a boss | `zoryth.spawn` |
| `/zoryth list` | List all registered bosses | `zoryth.list` |
| `/zoryth giveegg` | Give a boss spawn egg | `zoryth.giveegg` |
| `/zoryth kill` | Kill active bosses | `zoryth.kill` |
| `/zoryth reload` | Reload all configurations | `zoryth.reload` |
| `/zoryth debug` | Toggle debug mode | `zoryth.debug` |

*Note: The `zoryth.admin` permission grants access to all commands by default.*

---

## ⚙️ Configuration Features

Zoryth AI Boss comes with an extensive `config.yml` with several core modules:

### Performance & AI
- **AI Tick Rate:** Fully configurable update rates for AI (default: 2 ticks), target selection, and boss bars.
- **Targeting Modes:** Support for dynamic targeting strategies like `NEAREST`, `LOWEST_HEALTH`, `HIGHEST_HEALTH`, `HIGHEST_DAMAGE`, `RANDOM`, and `MOST_AGGRESSIVE`.
- **Dodge Mechanics:** Bosses have a configurable arrow dodge chance (e.g., 20%).

### Boss Bars
- Customizable default color (PINK, BLUE, RED, GREEN, YELLOW, PURPLE, WHITE).
- Customizable default styles (SOLID, SEGMENTED_6, SEGMENTED_10, etc.).
- Can display the current phase name and ability casting states in the title.
- Phase changes can smoothly animate the boss bar color.

### Arenas & Spawning
- **Arena Settings:** Set teleport delays before locking players, and unlock delays after the boss dies. Includes settings to block enderpearls and chorus fruit teleports.
- **Spawn Rules:** Limit boss spawning to specific worlds, set minimum online player requirements, and define auto-respawn delays.
- **WorldGuard Integration:** Prevent boss spawning in protected WorldGuard regions.

### Loot System
- **Loot Modes:** Choose between `PER_PLAYER` or `SHARED` loot distribution.
- **Minimum Damage Tracking:** Require a minimum damage percentage (e.g., 5.0%) to receive loot.
- Items can either drop at the boss location or go directly into the player's inventory.

---

## 🔌 Integrations (Soft-Dependencies)

- **PlaceholderAPI:** Display stats and boss information dynamically.
- **Vault:** Integration for economy rewards.
- **WorldGuard:** Prevent bosses from destroying or spawning in protected regions.
- **Citizens:** Support for NPC-based bosses and interactions.
