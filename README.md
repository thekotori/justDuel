# ⚔️ justDuel
A modern, high-performance, and network-ready dueling system, built for reliability and ease of use on any **Paper**, **Folia**, or **Spigot**-based server.

<p align="center">
<img src="https://img.shields.io/badge/Author-kotori-lightgrey?style=for-the-badge" alt="Author" />
<img src="https://img.shields.io/badge/API-1.21+-brightgreen?style=for-the-badge" alt="API Version" />
<img src="https://img.shields.io/badge/Platform-Paper_|_Folia-blue?style=for-the-badge" alt="Platform" />
</p>

---

## ✨ Features
- ⚔️ **Dual Duel Modes** — Choose between **KITS** mode for pre-configured loadouts or **SMP** mode to let players fight with their own inventory.  
- 🌐 **Full Cross-Server Support** — Instantly challenge and spectate players across your entire **BungeeCord** or **Velocity** network with seamless Redis integration.  
- 🛡️ **Advanced Kit System** — Players can create, edit, save, and publish their custom kits for others to use and rate in the public Kit Browser.  
- 🖥️ **Intuitive GUI Interface** — Manage everything through clean, modern, and user-friendly menus.  
- 🤖 **1v1 Queue NPC** — Spawn an interactive NPC for random duel matchmaking.  
- ⚙️ **Interactive Arena Setup** — Easily create unlimited duel arenas with a simple in-game setup tool.  
- ♻️ **Intelligent Arena Regeneration** — Arenas are automatically and efficiently reset after every duel.  
- 🚀 **High Performance** — Built with an asynchronous, non-blocking core and optimized for **Folia**.  
- 📊 **Detailed Stats & Leaderboards** — Track wins, losses, K/D ratio, W/L ratio, and server-wide leaderboards.  
- 👀 **Live Spectator Mode** — Watch ongoing duels in real time, even across servers.  
- 🎨 **Highly Customizable** — Full control over messages, GUIs, sounds, and behaviors with **MiniMessage** format.  
- 💾 **Flexible Storage** — Supports **SQLite** (single-server) and **MySQL/MariaDB** (network-wide).  
- 🧩 **PlaceholderAPI & Vault Support** — Display duel stats anywhere and reward winners with currency.  

---

## 📦 Installation
1. Download the latest `justDuel.jar`.  
2. Stop your Minecraft server.  
3. Place the file in your `/plugins/` directory.  
4. Install the required dependency: **Vault**.  
5. (Optional) Install **PlaceholderAPI** for placeholder support.  
6. Start the server to generate configuration files.  
7. Enter your license key and configure your database in `config.yml`.  
8. If using a network, configure your **Redis** settings in `config.yml`.  
9. Customize `config.yml`, `messages.yml`, and `gui.yml`.  
10. Reload the plugin with `/da reload`.  

---

## ⚙️ Configuration (config.yml explained)
```yaml
# License key received upon purchase.
license-key: 'ENTER_YOUR_LICENSE_KEY_HERE'

# Unique server identifier for cross-server features.
server-name: 'server1'

# Redis configuration (required for cross-server duels/spectating).
redis:
  enabled: false
  host: '127.0.0.1'
  port: 6379
  password: ''
  ssl: false

# Duel mode: 'KITS' or 'SMP'
duel-mode: KITS
countdown-seconds: 5
request-timeout-seconds: 60
request-cooldown-seconds: 10
wait-for-opponent-seconds: 15

kit-browser:
  enabled: true

kit-publishing:
  limits:
    - permission: 'justduel.publish.default'
      limit: 1
    - permission: 'justduel.publish.vip'
      limit: 5
    - permission: 'justduel.publish.admin'
      limit: 100

duel-rewards:
  enabled: false
  win-amount: 100.0

database:
  type: 'sqlite'
  # ... other database settings
```

---

## ⌨️ Commands & Permissions

### 🔧 Commands
| Command | Description | Permission |
|---------|-------------|------------|
| `/duel` | Opens the main duel menu. | `justduel.use` |
| `/duel <player>` | Challenges a player to a duel. | `justduel.use` |
| `/duel accept/deny` | Responds to the last duel request. | `justduel.use` |
| `/duel forfeit` | Forfeits your current duel. | `justduel.use` |
| `/duel leavequeue` | Leaves the duel queue. | `justduel.use` |
| `/duel savekit` | Saves your current kit. | `justduel.use` |
| `/duel stats [player]` | Shows duel statistics. | `justduel.use` |
| `/duel top [category]` | Displays leaderboards. | `justduel.use` |
| `/duel spectate [player]` | Spectates a duel / opens spectate menu. | `justduel.spectate` |
| `/duel leave` | Stops spectating a duel. | `justduel.spectate` |
| `/duel settings` | Opens your personal settings. | `justduel.use` |
| `/da arena setup <name>` | Interactive arena setup. | `justduel.admin` |
| `/da arena delete <name>` | Deletes an arena. | `justduel.admin` |
| `/da arena exit` | Cancels arena setup. | `justduel.admin` |
| `/da setspawn` | Sets global spawn. | `justduel.admin` |
| `/da spawn 1v1` | Spawns the 1v1 Queue NPC. | `justduel.admin` |
| `/da delete 1v1` | Deletes the 1v1 Queue NPC. | `justduel.admin` |
| `/da zones` | Shows arena/hub statuses. | `justduel.admin` |
| `/da syncconfigs` | Syncs `arenas.yml` to DB. | `justduel.admin` |
| `/da reload` | Reloads all configs. | `justduel.admin.reload` |

### 🔐 Permissions
| Permission | Description | Default |
|------------|-------------|---------|
| `justduel.admin` | Access to all admin commands. | op |
| `justduel.use` | Allows duel commands. | true |
| `justduel.spectate` | Allows spectating duels. | true |
| `justduel.bypass.cooldown` | Bypass duel cooldown. | op |
| `justduel.publish.<limit>` | Kit publishing limits. | op |
| `justduel.icon.<group>` | Allows specific kit icons. | varies |

---

## 🧩 PlaceholderAPI Placeholders
| Placeholder | Description |
|-------------|-------------|
| `%justduel_wins%` | Player's total duel wins. |
| `%justduel_losses%` | Player's total duel losses. |
| `%justduel_wlr%` | Win-loss ratio. |
| `%justduel_kills%` | Total duel kills. |
| `%justduel_deaths%` | Total duel deaths. |
| `%justduel_kdr%` | Kill-death ratio. |
| `%justduel_status%` | Current status (e.g., In Duel). |

---

<p align="center">Made with ❤️ by <strong>kotori</strong></p>
