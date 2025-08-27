# justDuel

A modern, high-performance, and network-ready dueling system, built for reliability and ease of use on any Paper, Folia, or Spigot-based server.

<p align="center">
  <img src="https://img.shields.io/badge/Author-kotori-lightgrey?style=for-the-badge" alt="Author" />
  <img src="https://img.shields.io/badge/API-1.21%2B-brightgreen?style=for-the-badge" alt="API Version" />
  <img src="https://img.shields.io/badge/Platform-Paper_|_Folia-blue?style=for-the-badge" alt="Platform" />
</p>

## ✨ Features

- ⚔️ **Dual Duel Modes** — Choose between **KITS** mode for pre-configured loadouts or **SMP** mode to let players fight with their own inventory.
- 🌐 **Full Cross-Server Support** — Instantly challenge and spectate players across your entire **BungeeCord** or **Velocity** network with seamless **Redis** integration.
- 🛡️ **Advanced Kit System** — Players can create, edit, save, and publish their custom kits for others to use and rate in the public **Kit Browser**.
- 🖥️ **Intuitive GUI Interface** — Manage everything through clean, modern, and user-friendly menus.
- 🤖 **1v1 Queue System** — Players can join a random 1v1 matchmaking queue via an interactive NPC or the simple `/duel queue 1v1` command.
- ⚙️ **Interactive Arena Setup** — Easily create unlimited duel arenas with a simple in-game setup tool. See the **How-To Guide** below.
- ♻️ **Automatic Arena Reset** — Placed blocks (like Cobwebs, Water, Lava) are automatically removed after each duel, keeping arenas clean.
- 🚀 **High Performance** — Built with an asynchronous, non-blocking core and optimized for **Folia**.
- 📊 **Detailed Stats & Leaderboards** — Track wins, losses, K/D ratio, and W/L ratio. You can even disable death tracking in duels to keep player stats clean.
- 👀 **Live Spectator Mode** — Watch ongoing duels in real time, even across servers.
- 🎨 **Highly Customizable** — Full control over messages, GUIs, sounds, and behaviors with **MiniMessage** format.
- 💾 **Flexible Storage** — Supports **SQLite** (single-server) and **MySQL/MariaDB** (network-wide).
- 🧩 **PlaceholderAPI & Vault Support** — Display duel stats anywhere with placeholders (including queue size!) and reward winners with currency.

---

## 📦 Installation

1. Download the latest `justDuel.jar`.
2. Stop your Minecraft server.
3. Place the file in your `/plugins/` directory.
4. Install the required dependency: **Vault**.
5. *(Optional)* Install **PlaceholderAPI** for placeholder support.
6. Start the server to generate configuration files.
7. Enter your license key and configure your database in `config.yml`.
8. If using a network, configure your **Redis** settings in `config.yml` for cross-server features to work.
9. Customize `config.yml`, `messages.yml`, and `gui.yml` to your liking.
10. Reload the plugin with `/da reload`.

---

## 📝 How-To Guides

### Creating a Duel Arena

Creating an arena is simple with the interactive setup tool. Each arena needs **two spawn points** for the players and **two corner points** to define its boundaries.

**Start the Setup**  
Go to the location of your arena and run the command:

```bash
/da arena setup <name>
```

`<name>` should be a unique name for your arena. If you have multiple arenas of the same type, use a number suffix (e.g., `castle-1`, `castle-2`).

**Use the Setup Tool**  
You will receive a **Blaze Rod** named **"Arena Setup Tool"**.

**Set Spawn Points**
- Left-click a block to set the first spawn point. You will receive a confirmation in chat.
- Left-click another block to set the second spawn point.

**Define Arena Boundaries**  
The boundaries define the rectangular area where players can fight and place/break blocks during a duel.
- Right-click a block in one corner of the arena to set **Position 1**.
- Right-click a block in the opposite, diagonal corner of the arena to set **Position 2**.

**Finish**
- Once all four points are set, the arena will be automatically saved and enabled. You'll get a completion message, and the setup tool will be removed.
- To cancel at any time: Type `/da arena exit`.

### Spawning the 1v1 Queue NPC

This NPC allows players to right-click it to join the random 1v1 matchmaking queue.

1. Go to the desired location for your NPC.
2. Run the command:
   ```bash
   /da spawn 1v1
   ```
3. The NPC will appear at your location. Its appearance and effects can be configured in `config.yml`.
4. To remove the NPC: Stand near it and run:
   ```bash
   /da delete 1v1
   ```

---

## ⚙️ Configuration (`config.yml` explained)

This file is the main control center for **justDuel**. Here are some key sections:

```yaml
# --- Player Defaults ---
# Set the default settings for new players.
player-defaults:
  # Should players receive a GUI pop-up for duel requests by default?
  # If false, they will only receive a chat message.
  gui-popup-for-requests: true

# --- Core Settings ---
# duel-mode: 'KITS' or 'SMP'
duel-mode: KITS
# ... other core settings

# --- Duel Settings ---
# If false, deaths during a duel will not be counted towards player stats.
track-deaths: true
# Commands allowed during a duel.
allowed-commands-in-duel: ["tell", "msg", "r", "pm", "w", "duel"]

# --- 1v1 Queue NPC ---
queue-npc:
  display-name: "<gradient:#00A8FF:#007AFF><bold>1v1 Random Queue</bold></gradient>"
  block-type: "DIAMOND_BLOCK"
  # ... animation settings
```

---

## ⌨️ Commands & Permissions

### 🔧 Commands

| Command | Description | Permission |
|---|---|---|
| `/duel` | Opens the main duel menu. | `justduel.use` |
| `/duel <player>` | Challenges a player to a duel. | `justduel.use` |
| `/duel accept/deny` | Responds to the last duel request. | `justduel.use` |
| `/duel toggle` | Toggles receiving duel requests. | `justduel.use` |
| `/duel queue 1v1` | Joins or leaves the random 1v1 queue. | `justduel.use` |
| `/duel forfeit` | Forfeits your current duel. | `justduel.use` |
| `/duel leavequeue` | Leaves the duel queue. | `justduel.use` |
| `/duel savekit` | Saves your current kit while in creation mode. | `justduel.use` |
| `/duel stats [player]` | Shows duel statistics for you or another player. | `justduel.use` |
| `/duel top [category]` | Displays leaderboards for a specific statistic. | `justduel.use` |
| `/duel spectate [player]` | Spectates a duel or opens the spectate menu. | `justduel.spectate` |
| `/duel leave` | Stops spectating a duel. | `justduel.spectate` |
| `/duel settings` | Opens your personal settings GUI. | `justduel.use` |
| `/da arena setup <name>` | Starts the interactive setup for an arena. | `justduel.admin` |
| `/da arena delete <name>` | Deletes an arena. | `justduel.admin` |
| `/da arena exit` | Cancels the current arena setup. | `justduel.admin` |
| `/da setspawn` | Sets the global spawn point for players after duels. | `justduel.admin` |
| `/da spawn 1v1` | Spawns the 1v1 Queue NPC at your location. | `justduel.admin` |
| `/da delete 1v1` | Deletes the 1v1 Queue NPC. | `justduel.admin` |
| `/da zones` | Shows the status of all arenas and hub zones. | `justduel.admin` |
| `/da syncconfigs` | Forces a sync of `arenas.yml` to the database. | `justduel.admin` |
| `/da reload` | Reloads all plugin configuration files. | `justduel.admin.reload` |

### 🔐 Permissions

| Permission | Description | Default |
|---|---|---|
| `justduel.admin` | Access to all `/da` admin commands. | `op` |
| `justduel.admin.reload` | Allows using `/da reload`. | `op` |
| `justduel.admin.build` | Allows building/breaking in arena worlds outside of duels. | `op` |
| `justduel.use` | Allows access to basic `/duel` commands. | `true` |
| `justduel.spectate` | Allows spectating ongoing duels. | `true` |
| `justduel.bypass.cooldown` | Bypasses the cooldown for sending duel requests. | `op` |
| `justduel.publish.*` | Gives access to all publishing limits. | `op` |
| `justduel.publish.default` | Default kit publishing limit. | `true` |
| `justduel.icon.*` | Gives access to all kit icons. | `op` |
| `justduel.icon.default` | Allows using default kit icons. | `true` |
| `justduel.icon.premium` | Allows using premium kit icons. | `op` |

---

## 🧩 PlaceholderAPI Placeholders

| Placeholder | Description |
|---|---|
| `%justduel_wins%` | Player's total duel wins. |
| `%justduel_losses%` | Player's total duel losses. |
| `%justduel_wlr%` | Player's win-loss ratio. |
| `%justduel_kills%` | Player's total duel kills. |
| `%justduel_deaths%` | Player's total duel deaths. |
| `%justduel_kdr%` | Player's kill-death ratio. |
| `%justduel_queue_size%` | The number of players in the 1v1 random queue. |

<br/>

<p align="center">Made with ❤️ by <strong>kotori</strong></p>
