# ⚔️ justDuel

A modern, high-performance, and network-ready dueling system, built for reliability and ease of use on any **Paper**, **Folia**, or **Spigot-based** server.

<p align="center">
  <img src="https://img.shields.io/badge/Author-kotori-lightgrey?style=for-the-badge" alt="Author" />
  <img src="https://img.shields.io/badge/API-1.21+-brightgreen?style=for-the-badge" alt="API Version" />
  <img src="https://img.shields.io/badge/Platform-Paper_|_Folia-blue?style=for-the-badge" alt="Platform" />
</p>

---

## ✨ Features

- ⚔️ **Dual Duel Modes** — Choose between **KITS** mode for pre-configured loadouts or **SMP** mode to let players fight with their own inventory.
- 🌐 **Full Cross-Server Support** — Instantly challenge and spectate players across your entire BungeeCord or Velocity network with seamless Redis integration.
- 🛡️ **Advanced Kit System** — Allow players to create, edit, save, and even **publish** their custom kits for others to use and rate in the public Kit Browser.
- 🖥️ **Intuitive GUI Interface** — Manage everything through clean, modern, and user-friendly menus, from challenging players to editing kits.
- ⚙️ **Dynamic Arena Management** — Create an unlimited number of duel arenas with simple in-game commands. The plugin handles arena allocation and regeneration automatically.
- ♻️ **Intelligent Arena Regeneration** — After each duel, arenas are instantly and efficiently restored to their original state, resetting only the blocks that were changed.
- 🚀 **High Performance** — Built with an asynchronous, non-blocking core to ensure zero lag, with native support for Folia's advanced scheduling.
- 📊 **Detailed Stats & Leaderboards** — Track wins, losses, K/D ratios, and W/L ratios. View personal stats or compete on server-wide leaderboards.
- 👀 **Live Spectator Mode** — Join and watch ongoing duels in real-time, even if they are happening on another server in your network.
- 🎨 **Highly Customizable** — Edit all messages, GUI layouts, sounds, and plugin behaviors to perfectly match your server's theme using MiniMessage format.
- 💾 **Flexible Storage** — Supports **SQLite** for single-server setups and **MySQL/MariaDB** for network-wide data synchronization.
- 🧩 **PlaceholderAPI & Vault Support** — Display player stats anywhere and reward duel winners with in-game currency.

---

## 📦 Installation

1.  Download the latest `justDuel.jar`.
2.  Stop your Minecraft server.
3.  Place the file in your `/plugins/` directory.
4.  *(Optional)* Install **PlaceholderAPI** for placeholder support.
5.  Start the server to generate the configuration files.
6.  Enter your **license key** and configure your **database** in `config.yml`.
7.  If you run a network, configure your **Redis** settings in `config.yml`.
8.  Customize `config.yml`, `messages.yml`, and `gui.yml` to your liking.
9.  Reload the plugin with `/dueladmin reload`.

---

## ⚙️ Configuration

### `config.yml` (Explained for Customers)

```yaml
# Enter the license key you received upon purchase.
license-key: 'ENTER_YOUR_LICENSE_KEY_HERE'

# A unique name for this server. Crucial for cross-server features to work correctly.
server-name: 'server1'

# Customize the sounds played when interacting with menus.
# Format: 'SOUND_NAME:volume:pitch'
gui-sounds:
  open: "BLOCK_CHEST_OPEN:1.0:1.0"
  click: "UI_BUTTON_CLICK:1.0:1.2"
  back: "BLOCK_WOODEN_DOOR_CLOSE:1.0:1.0"
  error: "BLOCK_ANVIL_LAND:1.0:1.5"

# Required for communication between multiple servers (cross-server duels, spectating, etc.).
redis:
  enabled: false
  host: '127.0.0.1'
  port: 6379
  password: ''
  ssl: false

# duel-mode: 'KITS' (players select from pre-defined or custom kits) or 'SMP' (players use their current inventory).
duel-mode: KITS
countdown-seconds: 5
request-timeout-seconds: 60 # Time a player has to accept a duel request.
request-cooldown-seconds: 10 # Cooldown before sending another request to the same player.

# Allows sending duel requests to players who are not inside a defined hub zone.
allow-duels-outside-hub: true

player-selector:
  # If true, the player selector GUI will show all players across the network (requires Redis).
  show-all-players: false

# Enables or disables the public kit browser and all related features.
kit-browser:
  enabled: true

# Define how many kits players can publish based on their permissions.
kit-publishing:
  limits:
    - permission: 'justduel.publish.default'
      limit: 1
    - permission: 'justduel.publish.vip'
      limit: 5
    - permission: 'justduel.publish.admin'
      limit: 100

# Requires Vault and an economy plugin (e.g., EssentialsX).
duel-rewards:
  enabled: false
  win-amount: 100.0

# Can be 'sqlite' or 'mysql'.
database:
  type: 'sqlite'
  # ... database settings
```

---

## ⌨️ Commands & Permissions

### 🔧 Commands

| Command | Description | Permission (justduel.command.*) |
|---------|-------------|---------------------------------|
| /duel | Opens the main duel menu. | justduel.use |
| /duel <player> | Challenges a player to a duel. | justduel.use |
| /duel accept/deny | Responds to the last duel request. | justduel.use |
| /duel forfeit | Forfeits your current duel. | justduel.use |
| /duel leavequeue | Leaves the duel queue. | justduel.use |
| /duel stats [player] | Shows duel statistics. | justduel.command.stats |
| /duel top [category] | Displays the leaderboards. | justduel.command.top |
| /duel spectate [player] | Spectates a duel or opens the menu. | justduel.spectate |
| /duel leave | Stops spectating a duel. | justduel.spectate |
| /dueladmin createarena <name> | Creates a new arena. | justduel.admin |
| /dueladmin setarenaspawn <arena> <1/2> | Sets a spawn point for an arena. | justduel.admin |
| /dueladmin setarenazone <arena> | Defines the boundaries for an arena. | justduel.admin |
| /dueladmin savearena <arena> | Saves and enables a configured arena. | justduel.admin |
| /dueladmin reload | Reloads all configuration files. | justduel.admin.reload |

### 🔐 Permissions

| Permission | Description | Default |
|------------|-------------|---------|
| justduel.admin | Grants access to all admin commands. | op |
| justduel.use | Allows players to use basic duel commands. | true |
| justduel.spectate | Allows players to spectate ongoing duels. | true |
| justduel.bypass.cooldown | Bypasses the duel request cooldown. | op |
| justduel.publish.<limit> | Permission nodes for kit publishing limits. | op |
| justduel.icon.<group> | Allows using specific groups of kit icons. | varies |

---

## 🧩 PlaceholderAPI

| Placeholder | Description |
|-------------|-------------|
| %justduel_wins% | Shows the player's total duel wins. |
| %justduel_losses% | Shows the player's total duel losses. |
| %justduel_wlr% | Shows the player's win-loss ratio. |
| %justduel_kills% | Shows the player's total duel kills. |
| %justduel_deaths% | Shows the player's total duel deaths. |
| %justduel_kdr% | Shows the player's kill-death ratio. |
| %justduel_status% | Shows the player's current status (e.g., In Duel). |

---

<p align="center">Made with ❤️ by <strong>kotori</strong></p>
