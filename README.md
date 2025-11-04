# JustDuel

<p align="center">
<img src="https://i.imgur.com/xiY0MQ7.png" alt="JustDuel Logo" width="1000"/>
</p>

<p align="center">
<strong>Enterprise-grade duel plugin for Paper/Folia with cross-server support, wagering, ELO system, and advanced arena management</strong>
</p>

<p align="center">
<img src="https://img.shields.io/badge/Version-4.0.0--DEV-brightgreen?style=for-the-badge" alt="Version" />
<img src="https://img.shields.io/badge/API-1.21+-blue?style=for-the-badge" alt="API Version" />
<img src="https://img.shields.io/badge/Java-21+-orange?style=for-the-badge" alt="Java" />
<img src="https://img.shields.io/badge/Folia-Supported-purple?style=for-the-badge" alt="Folia" />
</p>

<p align="center">
<a href="https://discord.gg/HRjcmEYXNy">
<img src="https://img.shields.io/discord/1389677354753720352?color=5865F2&label=Discord&logo=discord&logoColor=white&style=for-the-badge" alt="Discord" />
</a>
</p>

---

## 🎯 Overview

JustDuel is an **enterprise-grade PvP dueling plugin** designed for modern Minecraft servers running Paper, Purpur, Pufferfish, or Folia. Built from the ground up with performance, scalability, and reliability in mind, it supports everything from single servers to large-scale Velocity/BungeeCord networks with hundreds of concurrent players.

### ⚡ Key Features

#### 💰 Economy & Wagering
- **Full Vault Integration** - Bet currency on duels with escrow protection
- **Multi-Economy Support** - PlayerPoints, TokenManager, CoinsEngine
- **Server Tax System** - Configurable revenue sharing
- **High-Stakes Announcements** - Broadcast big wagers server-wide
- **Cross-Server Protection** - Prevents unfair economy exploitation

#### ⚔️ Advanced Duel System
- **Three Duel Modes** - KITS, SMP, SMP-HARD with unique mechanics
- **Smart Matchmaking** - Queue system with ELO-based pairing
- **Duel Requests** - Challenge specific players with custom settings
- **Right-Click Challenge** - Interact with players to open duel GUI
- **Spectator Mode** - Watch ongoing duels with dedicated view
- **Match Timers** - Configurable durations with sudden death mode

#### 🏟️ Arena System
- **Multi-Arena Support** - Unlimited arenas with automatic selection
- **WorldEdit Integration** - Easy arena creation and setup
- **Arena-Specific Queues** - Players can choose preferred arenas
- **Cross-Server Arenas** - Share arenas across your network
- **Build Mode** - In-arena building for setup

#### 🌍 Advanced World Management (NEW v4.0.0)
- **Temporary Worlds** - Auto-generated worlds for each duel
- **Schematic Arenas** - Paste WorldEdit schematics instantly
- **Pre-Generation System** - Zero-lag duel starts
- **Automatic Cleanup** - Smart world deletion after duels
- **Multiple Arena Types** - TEMPORARY, PERMANENT, SCHEMATIC
- **FastAsyncWorldEdit Support** - High-performance schematic pasting

#### 🎨 Kit Management
- **Predefined Kits** - Default, UHC, NoDebuff, and more
- **Custom Player Kits** - Players create and save their own loadouts
- **Kit Publishing** - Share kits with the community
- **Kit Browser** - Discover and use published kits
- **Permission-Based Limits** - Control publishing based on rank
- **Cross-Server Sync** - Sync kits across network servers

#### 🌐 Network Features
- **Redis Integration** - Real-time cross-server communication
- **MySQL/MariaDB Support** - Network-wide data persistence
- **Cross-Server Duels** - Challenge players on any server
- **Server Restrictions** - Prevent unfair cross-server matches
- **Network Statistics** - Unified stats across all servers
- **Global Leaderboards** - Network-wide rankings

#### 📊 Rating & Stats
- **ELO Rating System** - Skill-based matchmaking (experimental)
- **Comprehensive Statistics** - Wins, losses, K/D, streaks, and more
- **Win Streaks** - Track current and best streaks
- **Duel History** - View past matches and opponents
- **Leaderboards** - Top players by wins, kills, K/D, ELO
- **PlaceholderAPI** - Use stats in other plugins

#### 🎮 User Experience
- **Interactive GUIs** - Beautiful menus with MiniMessage formatting
- **Custom Scoreboards** - Dynamic scoreboards for lobby and duels
- **Action Bar Updates** - Real-time queue status and match info
- **Title Animations** - Countdown, victory, and defeat titles
- **Boss Bars** - Match timers and sudden death warnings
- **Sound Effects** - Customizable audio feedback
- **Particle Effects** - Smooth teleportation and visual feedback

#### 🚀 Performance & Optimization
- **200+ Concurrent Players** - Tested and optimized for high load
- **Async Operations** - Non-blocking database and Redis calls
- **Memory Management** - Smart caching with automatic cleanup
- **Connection Pooling** - HikariCP for optimal database performance
- **Thread-Safe** - ConcurrentHashMap and atomic operations
- **Folia Compatible** - Region-aware scheduling for multi-threaded servers

#### 🔧 Developer Features
- **Extensive API** - Create addons and integrations
- **Error Recovery** - Automatic crash recovery and state restoration
- **Health Monitoring** - Built-in system and connection monitoring
- **Debug Tools** - Comprehensive debugging and diagnostics
- **Configuration Sync** - Auto-sync configs across servers
- **Version Checker** - Automatic update notifications

---

## 📦 Installation

### Quick Start (Single Server)

1. **Download** `JustDuel-4.0.0-DEV.jar` from releases
2. **Place** in your server's `plugins` folder
3. **Restart** the server to generate configuration files
4. **Enter License Key** in `config.yml`:
   ```yaml
   license-key: 'YOUR_LICENSE_KEY_HERE'
   ```
5. **Configure** `config.yml` to your preferences
6. **Create Arenas** with `/da arena setup <name>`
7. **Reload** with `/da system reload`
8. **Done!** Players can now `/duel` each other

### Requirements

**Minimum Requirements:**
- Java 21 or higher
- Paper 1.21+ (or compatible fork)
- 2GB RAM minimum
- 1 vCPU core

**Recommended:**
- Java 21+
- Paper/Purpur/Pufferfish 1.21+
- 4GB+ RAM for 100+ players
- 2+ vCPU cores for optimal performance

**Supported Server Software:**
- ✅ Paper 1.21+
- ✅ Purpur 1.21+
- ✅ Pufferfish 1.21+
- ✅ Folia (multi-threaded)
- ✅ Canvas, Leaf, Airplane
- ❌ Spigot (not supported)
- ❌ Bukkit (not supported)

### Plugin Dependencies

**Optional but Recommended:**
- **[Vault](https://www.spigotmc.org/resources/vault.34315/)** - Required for wagering system and economy rewards
- **[PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/)** - Display stats in other plugins (holograms, scoreboards, chat)
- **Economy Plugin** - Any Vault-compatible economy (EssentialsX, CMI, etc.)

**For Cross-Server Networks:**
- **Redis Server** - Real-time cross-server communication
- **MySQL/MariaDB** - Network-wide data storage

### Installation Steps (Detailed)

#### Step 1: Pre-Installation
```bash
# Verify Java version
java -version  # Should show Java 21 or higher

# Verify Paper/compatible server
# Check your server startup script
```

#### Step 2: Install Plugin
```bash
# Stop your server
stop

# Place JustDuel-4.0.0-DEV.jar in plugins folder
# On Linux:
cp JustDuel-4.0.0-DEV.jar /path/to/server/plugins/

# Start server to generate configs
start
```

#### Step 3: Install Dependencies (Optional)
```bash
# If using wagering, install Vault and economy plugin
# Download Vault from: https://www.spigotmc.org/resources/vault.34315/
# Download EssentialsX from: https://essentialsx.net/downloads.html

# Place in plugins folder and restart
```

#### Step 4: Configure License
Edit `plugins/JustDuel/config.yml`:
```yaml
# Enter your license key from purchase
license-key: 'ABC123-DEF456-GHI789-JKL012'
```

#### Step 5: Configure Server Name
```yaml
# Unique identifier for this server (important for networks)
server-name: 'lobby-1'  # Change to: survival, skyblock, etc.
```

#### Step 6: Configure Duel Mode
```yaml
# Choose default duel mode
duel-mode: KITS  # Options: KITS, SMP, SMP-HARD
```

#### Step 7: Create First Arena
```bash
# In-game as admin/OP
/da arena setup my-first-arena

# Follow the prompts to set spawn points
# Use WorldEdit or manually set pos1 and pos2

# Exit setup mode when done
/da arena exit
```

#### Step 8: Test Installation
```bash
# Join queue
/duel queue

# Or challenge another player
/duel <playername>
```

### Cross-Server Setup (Advanced)

For network-wide duels across multiple servers in your Velocity/BungeeCord network:

#### Prerequisites
- ✅ Velocity or BungeeCord proxy
- ✅ MySQL/MariaDB server
- ✅ Redis server
- ✅ JustDuel installed on all servers

#### Step 1: Set Up MySQL Database

**Create Database:**
```sql
CREATE DATABASE justduel CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'justduel'@'%' IDENTIFIED BY 'your_secure_password';
GRANT ALL PRIVILEGES ON justduel.* TO 'justduel'@'%';
FLUSH PRIVILEGES;
```

**Configure Each Server** (`config.yml`):
```yaml
storage:
  type: mysql  # Change from sqlite to mysql
  mysql:
    host: 'mysql.yourserver.com'  # Your MySQL host
    port: 3306
    database: 'justduel'
    username: 'justduel'
    password: 'your_secure_password'
    
    # SSL for production (recommended)
    ssl:
      enabled: true
    
    # Connection pooling
    pool:
      minimum-idle: 2
      maximum-pool-size: 10
      connection-timeout: 30000
```

#### Step 2: Set Up Redis

**Install Redis:**
```bash
# Ubuntu/Debian
sudo apt-get install redis-server

# Or use Docker
docker run -d -p 6379:6379 redis:latest

# Or use managed service (AWS ElastiCache, Redis Labs, etc.)
```

**Configure Each Server** (`config.yml`):
```yaml
redis:
  enabled: true  # IMPORTANT: Must be true for cross-server
  host: 'redis.yourserver.com'  # Your Redis host
  port: 6379
  password: ''  # Set if using authentication
  ssl: false    # Enable for production
  
  # Connection pool (optimized settings)
  connection-pool:
    max-total: 32
    max-idle: 16
    min-idle: 4
    max-wait-ms: 3000
  
  # Auto-fix configuration issues
  auto-fix-config: true
  retry-on-failure: true
  max-retry-attempts: 3
```

#### Step 3: Configure Proxy Type

**For BungeeCord:**
```yaml
proxy-settings:
  proxy-type: BUNGEE
```

**For Velocity:**
```yaml
proxy-settings:
  proxy-type: VELOCITY
```

**Important:** Velocity requires:
- Modern forwarding enabled in Velocity config
- BungeeCord plugin messaging channel enabled

#### Step 4: Set Unique Server Names

**Each server must have a unique name:**

**Survival Server** (`config.yml`):
```yaml
server-name: 'survival'
```

**Skyblock Server** (`config.yml`):
```yaml
server-name: 'skyblock'
```

**Creative Server** (`config.yml`):
```yaml
server-name: 'creative'
```

#### Step 5: Configure Cross-Server Settings

```yaml
cross-server:
  # Primary method for cross-server communication
  primary-method: 'mysql'  # Recommended: stable and reliable
  
  mysql:
    # Sync intervals (lower = more real-time, higher = less load)
    sync-interval: 30              # General data sync
    arena-sync-interval: 15        # Arena availability
    kit-sync-interval: 30          # Custom kits
    stats-sync-interval: 60        # Player statistics
    request-check-interval: 5      # Duel requests (keep low)
    
    # Enable features
    enable-duels: true              # Cross-server duels
    enable-queue: true              # Cross-server queue
    enable-spectating: true         # Cross-server spectating
    enable-stats: true              # Unified statistics
    enable-leaderboards: true       # Network leaderboards
    enable-kits: true               # Shared custom kits
    enable-arenas: true             # Shared arenas
```

#### Step 6: Sync Arenas Across Servers

**Method 1: Automatic Sync**
```yaml
# In config.yml, enable arena sync
cross-server:
  mysql:
    enable-arenas: true
    arena-sync-interval: 15  # Check every 15 seconds
```

**Method 2: Manual Sync**
```bash
# After creating arenas on one server, sync to all servers
/da server syncarenas
```

#### Step 7: Test Cross-Server Setup

**On Server 1 (Survival):**
```bash
# Player A joins queue or challenges
/duel queue
```

**On Server 2 (Skyblock):**
```bash
# Player B should see Player A in queue
/duel queue

# Or Player A can challenge Player B
/duel PlayerB
```

**Match Found:**
- Both players teleported to arena server
- Duel starts automatically
- After duel, both return to origin servers

#### Step 8: Configure Server Restrictions

Protect players from unfair cross-server matches:

```yaml
server-restrictions:
  enabled: true  # HIGHLY RECOMMENDED for networks
  
  # Restrict modes by safety
  restrict-modes:
    KITS: false        # ✅ Safe - uses preset kits
    SMP: false         # ✅ Safe - items returned
    SMP-HARD: true     # ❌ BLOCK - items lost permanently
  
  # Block cross-server wagering (different economies)
  restrict-wagering: true  # RECOMMENDED
```

### Troubleshooting Installation

**Issue: License key invalid**
```bash
# Solution: Verify license key is entered exactly as provided
# Check for extra spaces or quotes
license-key: 'ABC-123-DEF-456'  # Correct
license-key: ' ABC-123-DEF-456'  # Wrong (extra space)
```

**Issue: Plugin not loading**
```bash
# Check Java version
java -version  # Must be 21+

# Check server software
# Paper 1.21+ required (Spigot not supported)
```

**Issue: Database connection failed**
```bash
# Verify MySQL credentials
mysql -h host -u username -p database

# Check firewall rules
telnet mysql-host 3306

# Verify database exists
SHOW DATABASES;
```

**Issue: Redis connection failed**
```bash
# Test Redis connection
redis-cli -h redis-host -p 6379 ping
# Should return: PONG

# Check Redis is running
sudo systemctl status redis
```

**Issue: Cross-server not working**
```bash
# Verify all servers have:
# 1. Same MySQL database configured
# 2. Redis enabled and connected
# 3. Unique server names
# 4. Same plugin version

# Check logs for errors
/da debug status
```

---

## 📝 Commands

### Player Commands

| Command | Description | Permission | Default |
|---------|-------------|------------|---------|
| `/duel` | Open main duel menu | `justduel.use` | Everyone |
| `/duel <player>` | Challenge a player to a duel | `justduel.use` | Everyone |
| `/duel <player> wager <amount>` | Challenge with currency wager | `justduel.use` | Everyone |
| `/duel accept` | Accept incoming duel request | `justduel.use` | Everyone |
| `/duel deny` | Deny incoming duel request | `justduel.use` | Everyone |
| `/duel queue` | Join random arena queue | `justduel.use` | Everyone |
| `/duel queue <kit>` | Join queue with specific kit | `justduel.use` | Everyone |
| `/duel queue <arena>` | Join specific arena queue | `justduel.use` | Everyone |
| `/duel leave` | Leave queue or forfeit duel | `justduel.use` | Everyone |
| `/duel leavequeue` | Leave matchmaking queue | `justduel.use` | Everyone |
| `/duel spectate <player>` | Spectate an ongoing duel | `justduel.spectate` | Everyone |
| `/duel stats` | View your duel statistics | `justduel.use` | Everyone |
| `/duel stats <player>` | View another player's stats | `justduel.use` | Everyone |
| `/duel settings` | Open settings GUI | `justduel.use` | Everyone |
| `/duel kit` | Open kit management GUI | `justduel.use` | Everyone |
| `/duel kit create <name>` | Create custom kit from inventory | `justduel.use` | Everyone |
| `/duel kit delete <name>` | Delete your custom kit | `justduel.use` | Everyone |
| `/duel kit publish <name>` | Publish kit for others to use | `justduel.publish.default` | Everyone |
| `/duel kit browse` | Browse published kits | `justduel.use` | Everyone |
| `/duel help` | Display help message | `justduel.use` | Everyone |

### Admin Commands

#### Arena Management
| Command | Description | Permission | Default |
|---------|-------------|------------|---------|
| `/da arena setup <name>` | Create new duel arena | `justduel.admin.arena` | OP |
| `/da arena exit` | Exit arena setup mode | `justduel.admin.arena` | OP |
| `/da arena delete <name>` | Remove existing arena | `justduel.admin.arena` | OP |
| `/da arena list` | List all configured arenas | `justduel.admin.arena` | OP |
| `/da arena status` | Check arena availability | `justduel.admin.arena` | OP |
| `/da arena validate` | Validate arena configuration | `justduel.admin.arena` | OP |
| `/da arena info <name>` | Show arena details | `justduel.admin.arena` | OP |
| `/da arena tp <name>` | Teleport to arena | `justduel.admin.arena` | OP |
| `/da arena setpos1` | Set arena position 1 | `justduel.admin.arena` | OP |
| `/da arena setpos2` | Set arena position 2 | `justduel.admin.arena` | OP |
| `/da arena setspawn 1` | Set spawn point 1 | `justduel.admin.arena` | OP |
| `/da arena setspawn 2` | Set spawn point 2 | `justduel.admin.arena` | OP |

#### Server Management
| Command | Description | Permission | Default |
|---------|-------------|------------|---------|
| `/da server syncarenas` | Sync arenas across servers | `justduel.admin.server` | OP |
| `/da server synckits` | Sync kits across servers | `justduel.admin.server` | OP |
| `/da server crossserver` | Manage cross-server features | `justduel.admin.server` | OP |
| `/da server status` | Show server status | `justduel.admin.server` | OP |
| `/da server info` | Show server information | `justduel.admin.server` | OP |

#### System Management
| Command | Description | Permission | Default |
|---------|-------------|------------|---------|
| `/da system reload` | Reload all configurations | `justduel.admin.system` | OP |
| `/da system reloadconfig` | Reload config.yml only | `justduel.admin.system` | OP |
| `/da system reloadmessages` | Reload messages.yml only | `justduel.admin.system` | OP |
| `/da system setspawn` | Set lobby spawn location | `justduel.admin.system` | OP |
| `/da system spawn 1v1` | Spawn queue NPC | `justduel.admin.system` | OP |
| `/da system delete 1v1` | Remove queue NPC | `justduel.admin.system` | OP |
| `/da system cleanup` | Clean duplicate holograms | `justduel.admin.system` | OP |
| `/da system maintenance` | Toggle maintenance mode | `justduel.admin.system` | OP |

#### Debug Commands
| Command | Description | Permission | Default |
|---------|-------------|------------|---------|
| `/da debug status` | Display debug information | `justduel.admin.debug` | OP |
| `/da debug log [on\|off]` | Toggle debug logging | `justduel.admin.debug` | OP |
| `/da debug diagnose` | Run system diagnostics | `justduel.admin.debug` | OP |
| `/da debug checkarenas` | Validate all arenas | `justduel.admin.debug` | OP |
| `/da debug cleardata <player>` | Clear player data | `justduel.admin.debug` | OP |
| `/da debug resetstats <player>` | Reset player statistics | `justduel.admin.debug` | OP |
| `/da debug testwager <amount>` | Test wagering system | `justduel.admin.debug` | OP |
| `/da debug checkredis` | Check Redis connection | `justduel.admin.debug` | OP |
| `/da debug checkdb` | Check database connection | `justduel.admin.debug` | OP |

#### Help Commands
| Command | Description | Permission | Default |
|---------|-------------|------------|---------|
| `/da help` | Show all admin commands | `justduel.admin` | OP |
| `/da help arena` | Arena management help | `justduel.admin` | OP |
| `/da help server` | Server management help | `justduel.admin` | OP |
| `/da help system` | System management help | `justduel.admin` | OP |
| `/da help debug` | Debug commands help | `justduel.admin` | OP |

### Command Aliases

**Player Aliases:**
- `/duel` → `/d`

**Admin Aliases:**
- `/dueladmin` → `/da`

### Command Examples

#### Basic Dueling
```bash
# Open main menu
/duel

# Challenge a player
/duel Steve

# Challenge with wager
/duel Steve wager 1000

# Accept incoming request
/duel accept

# Deny request
/duel deny

# Leave active duel
/duel leave
```

#### Queue System
```bash
# Join random queue
/duel queue

# Join with specific kit
/duel queue uhc

# Join specific arena
/duel queue arena1

# Leave queue
/duel leavequeue
# or click [LEAVE QUEUE] in action bar
```

#### Kit Management
```bash
# Open kit GUI
/duel kit

# Create kit from current inventory
/duel kit create my-pvp-kit

# Delete your kit
/duel kit delete my-pvp-kit

# Publish kit for others
/duel kit publish my-pvp-kit

# Browse published kits
/duel kit browse
```

#### Statistics
```bash
# View your stats
/duel stats

# View another player's stats
/duel stats Steve

# Compare stats
/duel stats Steve  # Then /duel stats to compare
```

#### Spectating
```bash
# Spectate a player in duel
/duel spectate Steve

# Leave spectator mode
/duel leave
```

#### Arena Setup
```bash
# Start arena creation
/da arena setup my-arena

# Set arena boundaries with WorldEdit
//wand
# Select region with WorldEdit

# Or manually set positions
/da arena setpos1
/da arena setpos2

# Set spawn points
/da arena setspawn 1
/da arena setspawn 2

# Exit setup
/da arena exit

# Validate arena
/da arena validate my-arena
```

#### Server Administration
```bash
# Reload all configs
/da system reload

# Set lobby spawn
/da system setspawn

# Spawn queue NPC at your location
/da system spawn 1v1

# Clean duplicate holograms
/da system cleanup

# Check system status
/da debug status

# Sync arenas across network
/da server syncarenas
```

---

## ⚙️ Configuration

### Core Configuration Files

| File | Purpose |
|------|---------|
| `config.yml` | Main settings, duel modes, wagering, server restrictions |
| `messages.yml` | All text output with MiniMessage hex color formatting |
| `arenas.yml` | Arena definitions and spawn locations |
| `kits.yml` | Predefined and custom kit configurations |
| `gui.yml` | GUI layouts, items, and menu configurations |
| `scoreboard.yml` | In-duel scoreboard display settings |
| `queue.yml` | Queue system and matchmaking settings |

### Key Configuration Options

**Duel Mode Settings (`config.yml`):**
```yaml
duel-mode: KITS              # Default mode: KITS, SMP, or SMP-HARD
countdown-seconds: 5         # Countdown before duel starts
request-timeout-seconds: 60  # Request expiration time
request-cooldown-seconds: 10 # Cooldown between requests
wait-for-opponent-seconds: 15 # Timeout for opponent join
```

**💰 Wagering System (`config.yml`):**
```yaml
wagering:
  enabled: false             # Master switch for wagering
  min-wager: 100.0           # Minimum bet amount
  max-wager: 10000.0         # Maximum bet amount (0 = unlimited)
  winner-percentage: 95      # Winner gets 95% of pot
  server-tax: 5              # Server gets 5% tax
  allow-in-queue: false      # Only allow in challenges
  refund-on-cancel: true     # Refund if duel cancelled
  refund-on-draw: true       # Refund if duel ends in draw
  economy-provider: 'vault'  # Economy plugin (vault/playerpoints/etc)
  
  announcements:
    enabled: true
    announce-threshold: 5000.0  # Announce wagers ≥ $5000
```

**🛡️ Server Restrictions (`config.yml`):**
```yaml
server-restrictions:
  enabled: true              # Master switch for restrictions
  restrict-modes:
    KITS: false              # ✅ Allow cross-server (uses preset kits - fair)
    SMP: false               # ✅ Allow cross-server (items returned - safe)
    SMP-HARD: true           # ❌ BLOCK cross-server (items lost - unfair!)
  restrict-wagering: true    # Block cross-server wagers (different economies)
  cross-server-blocked-message: '<#E74C3C>⚠ This mode is restricted to same-server only!'
```

**Database Settings (`config.yml`):**
```yaml
storage:
  type: sqlite              # sqlite, mysql, or mariadb
  mysql:
    host: '127.0.0.1'
    port: 3306
    database: 'justduel'
    username: 'root'
    password: 'your_password'
    pool:
      minimum-idle: 2
      maximum-pool-size: 10
```

**Redis Settings (`config.yml`):**
```yaml
redis:
  enabled: false            # Enable for cross-server support
  host: '127.0.0.1'
  port: 6379
  password: ''
  connection-pool:
    max-total: 32
    max-idle: 16
    min-idle: 4
```

---

## 💰 Wagering System

Players can bet currency on duels with full Vault integration and economy protection.

### How Wagering Works

**1. Challenge with Wager:**
```
/duel <player> wager 1000
```

**2. Escrow System:**
- Both players must accept the wager
- Funds are locked in escrow when duel starts
- No money is lost if duel is cancelled

**3. Distribution After Duel:**
```
Total Pot: $2000 (1000 from each player)
Server Tax (5%): $100
Remaining: $1900

Winner receives: $1805 (95% of remaining)
Loser receives: $95 (5% of remaining)

Winner Profit: +$805
Loser Loss: -$905
Server Tax Collected: $100
```

### Supported Economy Plugins

**Via Vault API:**
- EssentialsX Economy ✅
- CMI Economy ✅
- UltraEconomy ✅
- GemsEconomy ✅
- TheNewEconomy ✅
- And 50+ more Vault-compatible plugins!

**Direct Integration:**
- PlayerPoints (cross-server points)
- TokenManager (token economy)
- CoinsEngine (multi-currency)

### Wagering Features

- ✅ **Escrow Protection** - Funds locked during duel
- ✅ **Refund on Cancel** - Money returned if duel cancelled
- ✅ **Refund on Draw** - Money returned if draw
- ✅ **Server Tax** - Configurable percentage
- ✅ **Winner/Loser Split** - Customizable distribution
- ✅ **Min/Max Limits** - Prevent extreme wagers
- ✅ **High-Stakes Announcements** - Broadcast big duels
- ✅ **Cross-Server Protection** - Blocks unfair economy wagers
- ✅ **Network Currency** - Works with MySQL/Redis sync

---

## 🛡️ Server Restrictions

### Why Server Restrictions Matter

**The Problem:**
```
Skyblock Player Items: $18,000 custom gear
    vs
Survival Player Items: $270 basic diamond gear

In SMP-HARD mode (items lost on death):
❌ Skyblock player loses $18,000 in items
❌ Survival player loses $270 in items
❌ EXTREMELY UNFAIR!
```

**With Restrictions Enabled:**
```
✅ KITS mode: Cross-server allowed (uses preset kits - fair)
✅ SMP mode: Cross-server allowed (items returned after duel)
❌ SMP-HARD: BLOCKED for cross-server (items lost permanently!)
```

### Configuration

```yaml
server-restrictions:
  enabled: true
  restrict-modes:
    KITS: false      # ✅ Safe cross-server
    SMP: false       # ✅ Safe cross-server
    SMP-HARD: true   # ❌ BLOCK cross-server
  restrict-wagering: true  # Block cross-server wagers
```

---

## ⚔️ Duel Modes

JustDuel offers three distinct duel modes, each designed for different playstyles and scenarios.

### KITS Mode (Default & Recommended)

**Overview:**
Players fight using **predefined or custom kits** with equal gear, ensuring fair matches.

**How It Works:**
1. Player inventories are **cleared** before duel
2. Players receive **kit items** (armor, weapons, food, etc.)
3. After duel, kits are **removed** (items don't persist)
4. Players return to lobby with original inventory restored

**Available Kits:**
- **Default** - Diamond sword, bow, arrows, food
- **UHC** - Ultra Hardcore style with golden apples, building blocks
- **NoDebuff** - Splash potions, no debuff effects
- **Custom Player Kits** - Players create and save their own loadouts

**Advantages:**
- ✅ **Fair Competition** - Both players have equal gear
- ✅ **Cross-Server Safe** - No economy differences matter
- ✅ **Skill-Based** - Pure PvP skill determines winner
- ✅ **No Item Loss** - Original inventory preserved
- ✅ **Tournament Ready** - Perfect for competitive events

**Cross-Server:**
- ✅ **Allowed** - Players from different servers can duel safely
- No economy or item value differences affect fairness

**Best For:**
- Competitive PvP
- Tournaments and events
- Ranked matches
- ELO-based matchmaking
- Cross-server duels

**Configuration:**
```yaml
duel-mode: KITS

# Players can also choose mode per-duel in GUI
```

---

### SMP Mode (Survival Inventory)

**Overview:**
Players fight using their **current survival inventory**, with all items **returned** after the duel.

**How It Works:**
1. Player's **current inventory is saved**
2. Duel starts with **exact inventory** they had
3. After duel ends, **original inventory is restored** to both players
4. Winner and loser both get items back (no loss)

**Mechanics:**
- **Items Used During Duel:** Arrows shot, food eaten, potions used
- **Items Dropped:** All items dropped during duel are removed
- **Armor Durability:** Armor damage restored to pre-duel state
- **No Permanent Loss:** Everything restored regardless of outcome

**Advantages:**
- ✅ **Real Inventory** - Fight with your actual gear
- ✅ **Risk-Free** - No item loss on death
- ✅ **Practice Mode** - Test your loadout safely
- ✅ **Cross-Server Safe** - Items returned even if economies differ
- ✅ **Casual Friendly** - No stakes, just fun PvP

**Cross-Server:**
- ✅ **Allowed** - Safe for cross-server because items are returned
- Different item values don't matter since nothing is lost

**Best For:**
- Casual duels with friends
- Testing inventory loadouts
- Practice matches
- Friendly competitions
- Cross-server casual PvP

**Configuration:**
```yaml
duel-mode: SMP

# Can be combined with wagering for stakes without item loss
```

**Example Scenario:**
```
Before Duel:
  Player A: Diamond armor, sword, 32 steak
  Player B: Netherite armor, axe, 64 golden apples

During Duel:
  Player A eats 5 steak, breaks sword
  Player B uses 10 golden apples
  Player A wins

After Duel:
  Player A: Full inventory restored (32 steak, intact sword)
  Player B: Full inventory restored (64 golden apples)
  Both players back to pre-duel state
```

---

### SMP-HARD Mode (Hardcore Survival)

**Overview:**
Players fight using their **current inventory**, but items are **LOST PERMANENTLY** on death. High-stakes, high-reward mode.

**How It Works:**
1. Player's **current inventory used** (no backup saved)
2. Winner **keeps their items** (can claim opponent's drops)
3. Loser **LOSES ALL ITEMS** permanently on death
4. Items drop on ground for **200 seconds** (configurable)
5. After timeout, unclaimed items **despawn**

**Mechanics:**
- **Winner Claim Time:** 200 seconds to collect opponent's loot
- **Loser Penalty:** Loses entire inventory permanently
- **Item Drops:** All items drop naturally (armor, inventory, offhand)
- **No Protection:** Items can be stolen by others if arena is accessible
- **Restoration Timer:** Loser waits 200s before inventory restoration attempt

**Advantages:**
- ⚡ **High Stakes** - Real risk, real reward
- 💎 **Item Transfer** - Winner claims opponent's valuable items
- 🎯 **Skill Matters** - No room for error
- 🏆 **Bragging Rights** - Ultimate victory proof
- 💰 **Combine with Wagering** - Double stakes (items + money)

**Dangers:**
- ❌ **Permanent Loss** - Loser loses EVERYTHING
- ❌ **Cross-Server Unfair** - Different economy values
- ❌ **Item Theft** - Others can steal drops if not protected
- ❌ **No Refund** - Items gone forever

**Cross-Server:**
- ❌ **BLOCKED by default** - Prevents unfair matches
- Server restrictions protect players from economy exploitation

**Server Restriction Example:**
```
Skyblock Player Items: $18,000 worth of custom gear
    vs
Survival Player Items: $270 worth of basic diamond gear

If cross-server allowed:
❌ Skyblock player loses $18,000
❌ Survival player loses $270
❌ EXTREMELY UNFAIR!

With restrictions enabled:
✅ SMP-HARD blocked for cross-server
✅ Only same-server duels allowed
✅ Fair and balanced
```

**Best For:**
- High-stakes duels on same server
- Clan wars with item stakes
- Hardcore survival servers
- Economy sink for wealthy players
- Ultimate bragging rights

**Not Recommended For:**
- Cross-server networks (use KITS or SMP instead)
- New players
- Unbalanced economies
- Public servers without protections

**Configuration:**
```yaml
duel-mode: SMP-HARD

smp-hard:
  # Time for winner to claim items (seconds)
  winner-claim-time: 200
  
  # Clear items after timeout
  clear-items-after-timeout: true

server-restrictions:
  enabled: true
  restrict-modes:
    SMP-HARD: true  # Block cross-server (RECOMMENDED)
```

**Boss Bar Display:**
```
Winner sees:
⏰ SMP HARD VICTORY - 180s left to claim

Loser sees:
💀 SMP HARD DEFEAT - 180s left until restoration
```

**Example Scenario:**
```
Before Duel (Same Server):
  Player A: Full netherite, sword, 64 gaps
  Player B: Full diamond, axe, 32 steak

During Duel:
  Player A wins after intense battle
  Player B dies

After Duel:
  Player A: Keeps their items + can claim Player B's drops
  Player B: LOSES ALL ITEMS (netherite armor, sword, gaps)
  
Winner Claim Phase (200 seconds):
  Player A collects Player B's diamond armor and axe
  Timer expires
  Unclaimed items despawn
```

---

### Mode Comparison Table

| Feature | KITS | SMP | SMP-HARD |
|---------|------|-----|----------|
| **Inventory** | Preset kits | Current inventory | Current inventory |
| **Items After** | Removed | Restored | Lost (loser) |
| **Item Loss** | None | None | Permanent |
| **Cross-Server** | ✅ Allowed | ✅ Allowed | ❌ Blocked |
| **Fairness** | ✅ Equal gear | ⚠️ Varies | ⚠️ Varies |
| **Skill-Based** | ✅ Pure skill | ⚖️ Gear + Skill | ⚖️ Gear + Skill |
| **Wagering** | ✅ Compatible | ✅ Compatible | ✅ Compatible |
| **Risk Level** | None | None | Very High |
| **Best For** | Competition | Casual | Hardcore |

### Choosing the Right Mode

**Use KITS when:**
- Running tournaments or events
- Want fair, skill-based matches
- Need cross-server compatibility
- Implementing ELO rankings
- Competitive PvP focus

**Use SMP when:**
- Testing inventory loadouts
- Casual duels with friends
- Want real inventory without risk
- Cross-server casual PvP
- Practice matches

**Use SMP-HARD when:**
- Same-server only
- High-stakes, high-reward gameplay
- Hardcore survival environment
- Item economy sink needed
- Ultimate bragging rights

---

## �️ Arena Management

Create, configure, and manage unlimited duel arenas with ease.

### Creating Your First Arena

#### Step 1: Start Arena Setup
```bash
/da arena setup my-first-arena
```

You'll enter **Arena Setup Mode** where you can configure the arena.

#### Step 2: Set Arena Boundaries

**Option A: Using WorldEdit (Recommended)**
```bash
# Get WorldEdit wand
//wand

# Select arena region
# Left-click block for position 1
# Right-click block for position 2

# Boundaries automatically detected by JustDuel
```

**Option B: Manual Selection**
```bash
# Stand at corner 1 of arena
/da arena setpos1

# Stand at opposite corner of arena
/da arena setpos2
```

#### Step 3: Set Spawn Points
```bash
# Stand where Player 1 should spawn
/da arena setspawn 1

# Stand where Player 2 should spawn
/da arena setspawn 2
```

**Tip:** Face the direction you want players to spawn facing!

#### Step 4: Exit Setup Mode
```bash
/da arena exit
```

Arena is now saved and ready for use!

#### Step 5: Validate Arena
```bash
# Check if arena is properly configured
/da arena validate my-first-arena
```

### Arena Configuration Options

**Basic Settings:**
```yaml
# arenas.yml (auto-generated)
arenas:
  my-first-arena:
    # Arena display name
    name: "My First Arena"
    
    # World name
    world: "world"
    
    # Arena boundaries
    pos1:
      x: 100
      y: 64
      z: 100
    pos2:
      x: 150
      y: 100
      z: 150
    
    # Spawn points
    spawn1:
      x: 110.5
      y: 65.0
      z: 110.5
      yaw: 90.0
      pitch: 0.0
    spawn2:
      x: 140.5
      y: 65.0
      z: 140.5
      yaw: -90.0
      pitch: 0.0
    
    # Arena status
    enabled: true
    in-use: false
```

### Arena Management Commands

#### Listing Arenas
```bash
# Show all arenas
/da arena list

# Output:
# [Duel] Arenas (3):
# - my-first-arena (Available)
# - pvp-arena (In Use)
# - tournament-arena (Available)
```

#### Arena Status
```bash
# Check all arena statuses
/da arena status

# Shows:
# - Total arenas
# - Available arenas
# - In-use arenas
# - Disabled arenas
```

#### Arena Information
```bash
# Detailed info about specific arena
/da arena info my-first-arena

# Shows:
# - Name, world, positions
# - Spawn points
# - Current status
# - Last used time
```

#### Teleporting to Arena
```bash
# Teleport to arena spawn 1
/da arena tp my-first-arena
```

#### Deleting Arena
```bash
# Permanently delete arena
/da arena delete my-first-arena

# Confirmation required for safety
```

### Arena Features

#### Automatic Arena Selection
- Plugin automatically selects available arenas for duels
- Random selection ensures even distribution
- In-use arenas skipped automatically

#### Arena-Specific Queues
```bash
# Players can queue for specific arena
/duel queue my-first-arena
```

#### Multi-World Support
- Arenas can be in different worlds
- Automatic world loading and unloading
- World management optimization

#### Build Protection
- Block placement/breaking disabled in arenas (except setup mode)
- Prevents griefing during duels
- Configurable in `config.yml`

#### World Control
```yaml
world-control:
  # Lock time to day
  lock-time-to-day: true
  
  # Disable weather changes
  disable-weather-change: true
  
  # Disable mob spawning
  disable-mob-spawning: true
  
  # Disable phantom spawning
  disable-phantom-spawning: true
```

### Cross-Server Arena Sharing

Share arenas across your network for unified duel experience.

#### Enabling Arena Sync
```yaml
cross-server:
  mysql:
    enable-arenas: true
    arena-sync-interval: 15  # Sync every 15 seconds
```

#### Manual Arena Sync
```bash
# Sync arenas from this server to all network servers
/da server syncarenas
```

**How It Works:**
1. Create arena on Server A
2. Run `/da server syncarenas`
3. Arena appears on Server B, C, D, etc.
4. Players from any server can use the arena
5. Arena availability synced in real-time

### Arena Best Practices

#### Arena Size Recommendations
- **Small Arena:** 20x20 blocks (fast-paced PvP)
- **Medium Arena:** 30x30 blocks (standard duels)
- **Large Arena:** 50x50 blocks (UHC-style building)

#### Spawn Point Placement
- Place spawns facing each other for immediate engagement
- Ensure spawn points are on solid ground
- Test spawn points before going live

#### Arena Naming Conventions
```
Good Names:
- arena1, arena2, arena3 (simple, numbered)
- pvp-small, pvp-medium, pvp-large (descriptive)
- tournament-1, tournament-2 (purpose-based)

Bad Names:
- test, temp, asdf (not descriptive)
- "My Awesome Arena" (avoid spaces)
```

#### Multiple Arenas
- Create at least 3-5 arenas for busy servers
- More arenas = less waiting for players
- Mix different sizes and themes

---

## � Advanced World Management System

**NEW in v4.0.0** - JustDuel now includes a powerful world management system for arena generation, temporary worlds, and schematic-based arenas.

### Overview

The Advanced World Management System allows you to:
- ✅ **Create temporary worlds** for duels (automatic cleanup)
- ✅ **Paste schematics** for instant arena generation
- ✅ **Pre-generate worlds** for zero-lag duel starts
- ✅ **Automatic cleanup** of old/unused worlds
- ✅ **Multiple arena types** (TEMPORARY, PERMANENT, SCHEMATIC)

### Configuration

#### worlds.yml Setup

Create `worlds.yml` in your plugin folder with arena configurations:

```yaml
# World Manager Settings
world-manager:
  enabled: true                    # Enable advanced world management
  temporary-worlds: true           # Allow temporary world creation
  temp-world-prefix: "duel_temp_"  # Prefix for temporary worlds
  pre-generate-count: 2            # Pre-generate worlds for fast starts
  max-temp-worlds: 10              # Maximum temporary worlds allowed
  cleanup-delay-minutes: 5         # Time before temporary world deletion
  instant-cleanup: false           # Delete worlds immediately after duel

# Schematic Configuration
schematics:
  enabled: true                    # Enable schematic support (requires WorldEdit/FAWE)
  folder: "schematics/"            # Schematic folder path
  cache-schematics: true           # Cache schematics for performance
  max-cache-size: 10               # Maximum cached schematics

# Arena Configurations
arenas:
  "PvP-Arena-1":
    # Arena Type: TEMPORARY, PERMANENT, or SCHEMATIC
    type: TEMPORARY
    
    # World Settings
    environment: NORMAL              # NORMAL, NETHER, THE_END
    world-type: FLAT                 # FLAT, NORMAL, LARGE_BIOMES
    generator-settings: "minecraft:bedrock,2*minecraft:dirt,minecraft:grass_block;"
    
    # Spawn Configuration
    spawn:
      x: 0
      y: 65
      z: 0
      yaw: 0.0
      pitch: 0.0
    
    # World Border
    border:
      enabled: true
      radius: 50
      center-x: 0
      center-z: 0
      damage: 0.5
      warning-distance: 5
    
    # Regeneration Method
    regeneration-method: WORLD_COPY  # SCHEMATIC, WORLD_COPY, BLOCK_RESTORE
    
    # World Settings
    settings:
      disable-weather: true
      lock-time: true
      time: 6000                     # Noon
      disable-mobs: true
      disable-block-break: true
      disable-block-place: true

  "Schematic-Arena":
    type: SCHEMATIC
    schematic: "pvp_arena.schem"   # Schematic file name
    environment: NORMAL
    
    spawn:
      x: 0
      y: 65
      z: 0
    
    border:
      enabled: true
      radius: 50
    
    regeneration-method: SCHEMATIC
    
    settings:
      disable-weather: true
      lock-time: true
      time: 6000
      disable-mobs: true
```

### Arena Types

#### TEMPORARY Worlds
**Best for**: High-turnover servers with many simultaneous duels

- Creates a new world for each duel
- World is deleted after duel ends
- UUID-based naming prevents conflicts
- Pre-generation for instant duel starts

**Configuration Example:**
```yaml
arenas:
  "Temp-Arena":
    type: TEMPORARY
    world-type: FLAT
    generator-settings: "minecraft:bedrock,2*minecraft:dirt,minecraft:grass_block;"
    spawn: {x: 0, y: 65, z: 0}
```

**How It Works:**
1. Player starts duel → System creates `duel_temp_abc123`
2. Players teleported to fresh world
3. Duel completes → World scheduled for deletion
4. After 5 minutes (configurable) → World deleted

---

#### PERMANENT Worlds
**Best for**: Servers with few concurrent duels, reusable arenas

- Uses existing world
- Restores blocks after duel
- No world creation/deletion overhead
- Arena stays loaded

**Configuration Example:**
```yaml
arenas:
  "Main-Arena":
    type: PERMANENT
    source-world: "arena_world"    # Existing world name
    regeneration-method: BLOCK_RESTORE
    spawn: {x: 100, y: 70, z: 100}
```

**How It Works:**
1. Player starts duel → Teleported to existing world
2. Block changes tracked during duel
3. Duel completes → Blocks restored to original state
4. Arena immediately available for next duel

---

#### SCHEMATIC Worlds
**Best for**: Custom-designed arenas, professional server setups

- Pastes schematic for each duel
- Requires WorldEdit or FastAsyncWorldEdit
- Perfect for complex arena designs
- Instant regeneration

**Configuration Example:**
```yaml
arenas:
  "Tournament-Arena":
    type: SCHEMATIC
    schematic: "tournament_arena.schem"   # File in schematics/ folder
    environment: NORMAL
    spawn: {x: 0, y: 65, z: 0}
    regeneration-method: SCHEMATIC
```

**How It Works:**
1. Player starts duel → Schematic pasted into world
2. Players teleported to arena
3. Duel completes → Can instantly paste again or cleanup
4. Next duel → Schematic pasted fresh

**Supported Formats**: `.schem`, `.schematic`

---

### Pre-Generation System

**What is Pre-Generation?**

Pre-generation creates arena worlds **before** players start duels, eliminating world creation lag.

**Configuration:**
```yaml
world-manager:
  pre-generate-count: 3  # Keep 3 worlds ready at all times
```

**How It Works:**
1. Server starts → Creates 3 temporary worlds
2. Player starts duel → Uses pre-generated world (instant!)
3. System creates replacement world in background
4. Always maintains pool of ready worlds

**Performance Impact:**
- **Without Pre-Gen**: 2-5 second delay for world creation
- **With Pre-Gen**: 0 second delay (instant duel start)

---

### Schematic Integration

#### Installing WorldEdit/FAWE

**For Schematics Support:**

1. **Install WorldEdit** (basic support)
   - Download from [dev.bukkit.org](https://dev.bukkit.org/projects/worldedit)
   - Place in `plugins/` folder
   - Restart server

2. **Install FastAsyncWorldEdit** (recommended for performance)
   - Download from [hangar.papermc.io](https://hangar.papermc.io/IntellectualSites/FastAsyncWorldEdit)
   - Place in `plugins/` folder
   - Restart server

**JustDuel automatically detects which one is installed!**

#### Creating Schematics

**Step 1: Build Arena in Creative**
```bash
# Build your arena in a creative world
# Include spawn platforms, decorations, etc.
```

**Step 2: Select Arena with WorldEdit**
```bash
//wand               # Get WorldEdit wand
# Left-click and right-click to select region
```

**Step 3: Copy and Save**
```bash
//copy              # Copy selection
//schem save pvp_arena   # Save as pvp_arena.schem
```

**Step 4: Move Schematic**
```bash
# Move file from:
# plugins/WorldEdit/schematics/pvp_arena.schem
# to:
# plugins/JustDuel/schematics/pvp_arena.schem
```

**Step 5: Configure in worlds.yml**
```yaml
arenas:
  "PvP-Arena-1":
    type: SCHEMATIC
    schematic: "pvp_arena.schem"
```

---

### Maintenance & Cleanup

#### Automatic Cleanup

The system automatically maintains worlds:

```yaml
maintenance:
  cleanup-interval-minutes: 5    # Run cleanup every 5 minutes
  max-world-age-minutes: 30      # Delete worlds older than 30 minutes
  auto-cleanup-on-startup: true  # Clean old worlds on server start
```

**What Gets Cleaned:**
- Temporary worlds from crashed duels
- Worlds older than `max-world-age-minutes`
- Empty worlds with no players

**What Stays:**
- PERMANENT type worlds
- Worlds currently in use
- Pre-generated worlds in the pool

#### Manual Cleanup Commands

```bash
# Force cleanup of old temporary worlds
/da world cleanup

# List all managed worlds
/da world list

# Delete specific world
/da world delete duel_temp_abc123
```

---

### Performance Optimization

#### Memory Settings

For servers with many temporary worlds:

```yaml
performance:
  unload-empty-worlds: true       # Unload worlds with no players
  unload-delay-seconds: 300       # Wait 5 minutes before unload
  force-garbage-collection: false # Force GC after world deletion
  max-concurrent-world-ops: 3     # Max parallel world operations
```

#### Recommended Server Settings

**For High-Traffic Servers (20+ players):**
```yaml
world-manager:
  pre-generate-count: 5
  max-temp-worlds: 15
  instant-cleanup: false
  cleanup-delay-minutes: 3
```

**For Low-Traffic Servers (< 10 players):**
```yaml
world-manager:
  pre-generate-count: 2
  max-temp-worlds: 5
  instant-cleanup: true
  cleanup-delay-minutes: 1
```

---

### Debug Mode

Enable detailed logging to troubleshoot world management:

```yaml
debug:
  enabled: true
  log-world-creation: true
  log-world-deletion: true
  log-maintenance: true
  log-schematic-operations: true
```

**Sample Debug Output:**
```
[WorldManager] Creating arena world: PvP-Arena-1 (type: TEMPORARY)
[WorldManager] Pre-generating 2 worlds for faster duel starts
[SchematicManager] Pasting schematic: pvp_arena.schem at PvP-Arena-1
[WorldManager] Maintenance: Cleaning up 1 old worlds
[WorldManager] Deleted world: duel_temp_abc123 (age: 10 minutes)
```

---

### Migration from Legacy System

**Upgrading from Old Arena System:**

1. ✅ **Existing arenas continue to work** - No changes required!
2. ✅ **worlds.yml is optional** - Only for advanced features
3. ✅ **Gradual migration** - Add world configs as needed

**To Enable for Existing Arena:**
```yaml
# In worlds.yml, reference your existing arena
arenas:
  "existing-arena-name":
    type: PERMANENT
    source-world: "world"    # Your arena's world
    # No need to change spawn points - uses database values
```

---

### Cross-Server World Management

**Arena worlds work seamlessly across servers!**

**Configuration:**
```yaml
cross-server:
  mysql:
    enable-worlds: true          # Sync world configs
    world-sync-interval: 30      # Sync every 30 seconds
```

**How It Works:**
1. **Server A**: Player challenges someone on Server B
2. **Server A**: Checks if arena exists on Server B
3. **Server B**: Creates/prepares arena world
4. **Both**: Players teleported and duel starts
5. **Server B**: Cleans up world after duel

**Arena Creation Priority:**
- First checks if arena world exists locally
- Falls back to world configuration from database
- Creates temporary world if configured
- All synchronized via Redis + MySQL

---

### Troubleshooting

#### "WorldEdit not found - Schematic features disabled"
**Solution**: Install WorldEdit or FastAsyncWorldEdit plugin

#### "Max temporary worlds limit reached"
**Solution**: Increase `max-temp-worlds` or enable `instant-cleanup`

#### "Schematic file not found"
**Solution**: Check file exists in `plugins/JustDuel/schematics/`

#### "World creation taking too long"
**Solution**: Enable pre-generation with `pre-generate-count: 3`

#### "Worlds not being deleted"
**Solution**: Check `cleanup-delay-minutes` setting and maintenance task logs

---

## �🎨 Kit System

Comprehensive kit management with custom player kits, publishing, and cross-server syncing.

### Predefined Kits

JustDuel includes several default kits ready to use:

#### Default Kit
```yaml
# Basic PvP kit
Items:
  - Diamond Sword
  - Bow
  - 64x Arrow
  - 64x Cooked Beef

Armor:
  - Diamond Helmet
  - Diamond Chestplate
  - Diamond Leggings
  - Diamond Boots
```

#### UHC Kit
```yaml
# Ultra Hardcore style
Items:
  - Diamond Sword
  - Bow
  - Fishing Rod
  - 8x Golden Apple
  - 64x Arrow
  - Lava Bucket
  - Water Bucket
  - 64x Cobblestone

Armor:
  - Diamond Helmet
  - Diamond Chestplate
  - Diamond Leggings
  - Diamond Boots
```

#### NoDebuff Kit
```yaml
# Splash potions, no debuffs
Items:
  - Diamond Sword
  - 8x Splash Potion of Healing II
  - 4x Splash Potion of Speed II
  - 2x Splash Potion of Fire Resistance
  - 64x Cooked Beef

Armor:
  - Diamond Helmet (Protection IV)
  - Diamond Chestplate (Protection IV)
  - Diamond Leggings (Protection IV)
  - Diamond Boots (Protection IV, Feather Falling IV)
```

### Custom Player Kits

Players can create, save, and share their own kits.

#### Creating Custom Kit

**Step 1: Prepare Your Inventory**
```bash
# Equip the items you want in the kit
# - Armor in armor slots
# - Items in inventory slots
# - Offhand item if desired
```

**Step 2: Create Kit from Inventory**
```bash
/duel kit create my-pvp-kit

# Kit saved! You'll receive confirmation message
```

**Step 3: Test Your Kit**
```bash
# Join queue with your custom kit
/duel queue my-pvp-kit

# Or challenge with your kit via GUI
```

#### Managing Custom Kits

**View Your Kits**
```bash
# Open kit management GUI
/duel kit
```

**Delete Kit**
```bash
/duel kit delete my-pvp-kit
```

**Rename Kit** (via GUI)
1. Open `/duel kit`
2. Right-click kit to rename
3. Type new name in chat

#### Kit Publishing System

Share your kits with other players on your server or network.

**Publishing a Kit**
```bash
# Publish your kit for others to use
/duel kit publish my-pvp-kit
```

**Permission-Based Limits:**
```yaml
kit-publishing:
  limits:
    - permission: 'justduel.publish.default'
      limit: 1     # Default players: 1 published kit
    
    - permission: 'justduel.publish.vip'
      limit: 5     # VIP players: 5 published kits
    
    - permission: 'justduel.publish.premium'
      limit: 10    # Premium players: 10 published kits
    
    - permission: 'justduel.publish.admin'
      limit: 100   # Admins: 100 published kits
```

**Browsing Published Kits**
```bash
# Open kit browser
/duel kit browse

# Browse community-created kits
# Click to use in duels
```

**Published Kit Features:**
- **Author Attribution** - Shows who created the kit
- **Usage Stats** - See how many times kit was used
- **Rating System** - Players can rate kits (future feature)
- **Cross-Server Sync** - Published kits shared across network

### Kit Icons

Customize kit appearance in GUIs with permission-based icons.

```yaml
kit-icons:
  default:
    permission: 'justduel.icon.default'
    materials:
      - STONE_SWORD
      - IRON_SWORD
      - BOW
      - CROSSBOW
      - SHIELD
  
  premium:
    permission: 'justduel.icon.premium'
    materials:
      - DIAMOND_SWORD
      - GOLDEN_SWORD
      - TRIDENT
      - DIAMOND_AXE
      - ENCHANTED_BOOK
  
  admin:
    permission: 'justduel.icon.admin'
    materials:
      - NETHERITE_SWORD
      - DRAGON_HEAD
      - TOTEM_OF_UNDYING
      - NETHER_STAR
      - ELYTRA
```

### Cross-Server Kit Syncing

Sync custom kits across your network so players have them on all servers.

```yaml
cross-server:
  mysql:
    enable-kits: true
    kit-sync-interval: 30  # Sync every 30 seconds
```

**Manual Kit Sync:**
```bash
/da server synckits
```

### Kit Best Practices

#### Creating Balanced Kits
- **Equal Power Level** - Kits should be similarly balanced
- **No Overpowered Items** - Avoid items that give unfair advantage
- **Test Before Publishing** - Duel with kit first to ensure balance

#### Kit Naming
```
Good Names:
- speed-pvp (descriptive)
- pot-loadout (clear purpose)
- uhc-pro (style indicator)

Bad Names:
- kit123 (not descriptive)
- test (too generic)
- asdfg (meaningless)
```

#### Managing Many Kits
- Organize kits by purpose (pvp, uhc, nodebuff)
- Delete unused kits regularly
- Publish only your best kits

---

## 🎯 Queue & Matchmaking System

Advanced matchmaking system with multiple queue types, action bar updates, and ELO-based pairing.

### Queue Types

#### Random Queue
Join a queue with random arena and kit selection.

```bash
# Join random queue
/duel queue

# Matches you with next available opponent
# Random arena selected automatically
# Default kit used
```

#### Kit-Specific Queue
Join queue with a specific kit.

```bash
# Queue with predefined kit
/duel queue uhc

# Queue with your custom kit
/duel queue my-pvp-kit

# Only matches with players using same kit
```

#### Arena-Specific Queue
Join queue for a specific arena.

```bash
# Queue for specific arena
/duel queue arena1

# Only matches on that arena
# Random kit selection
```

### How Matchmaking Works

#### Matching Algorithm
1. **Find Eligible Players**
   - Players in same queue type
   - Not already in duel
   - Same server or cross-server allowed

2. **Select Match**
   - First-in-first-out (FIFO) by default
   - ELO-based matching if enabled
   - Cross-server considerations

3. **Prepare Match**
   - Reserve arena
   - Teleport both players
   - Apply kits
   - Start countdown

4. **Start Duel**
   - 5-second countdown
   - Display titles and boss bars
   - Begin match

#### ELO-Based Matchmaking

Match players of similar skill levels (experimental feature).

```yaml
elo-system:
  enabled: true
  
  matchmaking:
    enabled: true
    # Maximum ELO difference for matching
    max-rating-difference: 200
    
    # Increase tolerance over time
    rating-tolerance-increase: 50  # Per 30 seconds in queue
```

**How It Works:**
```
Player A (ELO: 1500) joins queue
Player B (ELO: 1520) joins queue
→ Matched (difference: 20, within 200 limit)

Player C (ELO: 1500) joins queue
Player D (ELO: 1800) joins queue
→ Not matched initially (difference: 300)
→ After 30 seconds, tolerance increases to 250
→ After 60 seconds, tolerance increases to 300
→ Now matched
```

### Action Bar Updates

Real-time queue status displayed in action bar.

**While in Queue:**
```
⏳ In Queue for Random Arena (15s) [LEAVE QUEUE]
```

**Clickable Leave Button:**
- Click `[LEAVE QUEUE]` to exit queue instantly
- Or use `/duel leave` command

**Action Bar Configuration:**
```yaml
queue:
  action-bar:
    enabled: true
    update-interval: 10  # ticks (0.5 seconds)
    
    messages:
      # Specific arena queue
      arena-specific: '<#5DADE2>⏳ In Queue for <white><arena></white> (<time>s) <#E74C3C><bold>[<click:run_command:/duel leavequeue><hover:show_text:Click to leave queue>LEAVE QUEUE</hover></click>]</bold></#E74C3C>'
      
      # Random arena queue
      random-arena: '<#5DADE2>⏳ In Queue for <white>Random Arena</white> (<time>s) <#E74C3C><bold>[<click:run_command:/duel leavequeue><hover:show_text:Click to leave queue>LEAVE QUEUE</hover></click>]</bold></#E74C3C>'
```

### Queue Success Messages

When you join queue, you see a success message:

```
✅ Queued for Random Arena! [LEAVE QUEUE]
```

**Configuration:**
```yaml
queue:
  success-messages:
    arena-specific: '<#2ECC71>✓ Queued for <white><arena></white>! <#E74C3C><bold>[<click:run_command:/duel leavequeue>LEAVE QUEUE</click>]</bold></#E74C3C>'
    
    random-arena: '<#2ECC71>✓ Queued for <white>Random Arena</white>! <#E74C3C><bold>[<click:run_command:/duel leavequeue>LEAVE QUEUE</click>]</bold></#E74C3C>'
```

### Leaving Queue

Multiple ways to leave the queue:

```bash
# Command
/duel leave
/duel leavequeue

# Click action bar message
# Click [LEAVE QUEUE] button

# Automatically removed when:
# - Match found
# - Player disconnects
# - Player starts another duel
# - Player changes servers
```

### Cross-Server Queue

Queue with players across your entire network.

```yaml
cross-server:
  mysql:
    enable-queue: true  # Enable cross-server queue
```

**How Cross-Server Queue Works:**
1. Player on Server A joins queue
2. Player on Server B joins queue
3. Plugin matches them via MySQL
4. Both players teleported to arena server
5. After duel, each returns to origin server

### Queue Customization

**Queue Settings:**
```yaml
# config.yml
queue:
  # Action bar updates
  action-bar:
    enabled: true
    update-interval: 10  # How often to update (ticks)
  
  # Match timeout
  max-wait-time: 300  # Max seconds in queue (5 minutes)
  
  # Queue position
  show-position: true  # Show position in queue
```

### Queue NPC

Spawn an interactive NPC for queuing.

#### Spawning Queue NPC
```bash
# Stand where you want NPC
/da system spawn 1v1
```

**NPC Features:**
- **Right-Click to Queue** - Interact to join random queue
- **Hologram Display** - Shows "1v1 Random Queue"
- **Particle Effects** - Enchantment particles
- **Animation** - Bobbing and rotating

**NPC Configuration:**
```yaml
queue-npc:
  display-name: "<#00A8FF><bold>1v1 Random Queue</bold></#00A8FF>"
  block-type: "DIAMOND_BLOCK"
  particle-effect: "ENCHANT"
  
  animation:
    bobbing: true
    bobbing-height: 0.25
    bobbing-speed: 0.02
    rotation: true
    rotation-speed: 0.05
```

#### Removing Queue NPC
```bash
/da system delete 1v1
```

### Queue Troubleshooting

**Issue: Not finding matches**
- Check if other players are in queue: `/da debug status`
- Ensure cross-server is configured if needed
- Try random queue instead of specific arena/kit

**Issue: Queue position not updating**
- Verify action bar is enabled in config
- Check for plugin conflicts affecting action bars

**Issue: Cross-server queue not working**
- Verify MySQL is connected
- Ensure `enable-queue: true` in cross-server settings
- Check Redis is connected for real-time updates

---

## 📊 Statistics & Leaderboards

Track player performance with comprehensive stats and leaderboards.

### Tracked Statistics

| Stat | Description |
|------|-------------|
| **Wins** | Total duel victories |
| **Losses** | Total duel defeats |
| **Win Rate** | Percentage of duels won |
| **Kills** | Total kills in duels |
| **Deaths** | Total deaths in duels |
| **K/D Ratio** | Kills divided by deaths |
| **Current Streak** | Consecutive wins |
| **Best Streak** | Highest win streak achieved |
| **Total Duels** | Total duels participated in |
| **Last Duel** | Time since last duel |

### View Statistics

```
/duel stats              # View your stats
/duel stats <player>     # View another player's stats
```

### Example Display

```
⚔ Combat & PvP Statistics
  ✓ 45 Wins | ✗ 12 Losses | 📊 78.95% Win Rate
  💀 156 Kills | 💔 38 Deaths | ⚖ 4.11 K/D Ratio

🔥 Streak Information
  Current: 3 wins | Best: 12 wins

📈 Activity
  Total Duels: 57 | Last: 2 hours ago
```

---

## 🔌 PlaceholderAPI Integration

Use JustDuel placeholders in other plugins (scoreboards, holograms, chat, etc.)

### Player Statistics

```
%justduel_wins%              # Total wins
%justduel_losses%            # Total losses
%justduel_wlr%               # Win/loss ratio
%justduel_kills%             # Total kills
%justduel_deaths%            # Total deaths
%justduel_kdr%               # Kill/death ratio
%justduel_win_streak%        # Current win streak
%justduel_best_streak%       # Best win streak
%justduel_total_duels%       # Total duels
%justduel_in_duel%           # true/false if in duel
```

### Leaderboard Placeholders

```
%justduel_top_wins_<position>_name%
%justduel_top_wins_<position>_value%
%justduel_top_kills_<position>_name%
%justduel_top_kdr_<position>_value%
```

Example: `%justduel_top_wins_1_name%` shows #1 player by wins

---

## 🚀 Performance Optimization

JustDuel is optimized to support **200+ concurrent players** with these features:

### Memory Management
- ✅ SoftReference caching for ItemStacks
- ✅ ConcurrentHashMap for thread-safe collections
- ✅ Automatic cache invalidation
- ✅ Memory-efficient GUI system

### Database Optimization
- ✅ HikariCP connection pooling
- ✅ Async database operations
- ✅ Batch stat updates (20 tick intervals)
- ✅ Prepared statements (SQL injection safe)

### Thread Safety
- ✅ ConcurrentHashMap for NPC tracking
- ✅ ConcurrentHashMap for GUI sessions
- ✅ AtomicLong for counters
- ✅ Bukkit/Folia scheduler awareness

### Expected Performance (200 Players)

| Metric | Target | Status |
|--------|--------|--------|
| TPS | >19.0 | ✅ |
| Memory | ~700MB | ✅ |
| Database Queries | <50ms | ✅ |
| GUI Operations | <100ms | ✅ |
| Death Respawn | <1ms | ✅ |

Track player performance with comprehensive statistics and global leaderboards.

### Tracked Statistics

| Stat | Description | Storage |
|------|-------------|---------|
| **Wins** | Total duel victories | Database |
| **Losses** | Total duel defeats | Database |
| **Win Rate** | Percentage of duels won | Calculated |
| **W/L Ratio** | Wins divided by losses | Calculated |
| **Kills** | Total kills in duels | Database |
| **Deaths** | Total deaths in duels | Database |
| **K/D Ratio** | Kills divided by deaths | Calculated |
| **Current Streak** | Consecutive wins | Database |
| **Best Streak** | Highest win streak achieved | Database |
| **Total Duels** | Total duels participated in | Calculated |
| **ELO Rating** | Skill rating (if enabled) | Database |
| **Last Duel** | Timestamp of last duel | Database |

### Viewing Statistics

**Your Own Stats:**
```bash
/duel stats
```

**Another Player's Stats:**
```bash
/duel stats Steve
```

### Statistics Display

**Example Output:**
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
        DUEL STATISTICS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

👤 Player: Steve

⚔️ Combat & PvP Statistics
  ✓ 45 Wins | ✗ 12 Losses | 📊 78.95% Win Rate
  ⚖️ 3.75 W/L Ratio
  💀 156 Kills | 💔 38 Deaths | ⚖ 4.11 K/D Ratio

🔥 Streak Information
  Current: 3 wins | Best: 12 wins

📈 Activity
  Total Duels: 57
  Last Duel: 2 hours ago

🏆 ELO Rating: 1547
  Rank: Gold II

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Leaderboards

**Top Players by Wins:**
```
1. Steve - 450 wins
2. Alex - 398 wins
3. Notch - 367 wins
...
```

**Top Players by K/D:**
```
1. Steve - 5.32 K/D
2. Alex - 4.87 K/D
3. Notch - 4.21 K/D
...
```

**Leaderboard Updates:**
- Real-time updates after each duel
- Network-wide rankings with MySQL
- Cached for performance (120-second intervals)

### Cross-Server Statistics

Unified stats across your entire network.

```yaml
cross-server:
  mysql:
    enable-stats: true
    stats-sync-interval: 60  # Sync every 60 seconds
    
    enable-leaderboards: true
    leaderboard-sync-interval: 120  # Update every 2 minutes
```

**Features:**
- Same stats on all servers
- Global leaderboards
- Real-time synchronization
- Historical data preservation

---

## 🎖️ ELO Rating System (Experimental)

Advanced skill-based rating system for competitive matchmaking.

### What is ELO?

ELO is a rating system that calculates the relative skill levels of players:
- **Win vs Higher ELO:** Gain more points
- **Win vs Lower ELO:** Gain fewer points
- **Loss vs Higher ELO:** Lose fewer points
- **Loss vs Lower ELO:** Lose more points

### Enabling ELO System

```yaml
elo-system:
  # Enable ELO rating system
  enabled: true
  
  # Starting ELO for new players
  starting-rating: 1200
  
  # Minimum ELO (floor)
  minimum-rating: 600
  
  # Maximum ELO (soft cap)
  maximum-rating: 3000
  
  # K-factor (rating volatility)
  k-factor: 32  # Higher = more volatile changes
```

### ELO Calculation

**Basic Formula:**
```
Expected Score = 1 / (1 + 10^((Opponent ELO - Your ELO) / 400))
New ELO = Old ELO + K * (Actual Score - Expected Score)

Actual Score:
- Win = 1.0
- Loss = 0.0
- Draw = 0.5
```

**Example:**
```
Player A (ELO: 1500) vs Player B (ELO: 1400)

Expected Score for A: 0.64 (64% win chance)
Expected Score for B: 0.36 (36% win chance)

If A wins:
  A's new ELO = 1500 + 32 * (1.0 - 0.64) = 1511
  B's new ELO = 1400 + 32 * (0.0 - 0.36) = 1388

If B wins (upset):
  A's new ELO = 1500 + 32 * (0.0 - 0.64) = 1479 (-21 points)
  B's new ELO = 1400 + 32 * (1.0 - 0.36) = 1420 (+20 points)
```

### ELO-Based Matchmaking

Match players of similar skill levels.

```yaml
elo-system:
  matchmaking:
    enabled: true
    
    # Maximum ELO difference for matching
    max-rating-difference: 200
    
    # Increase tolerance over time (per 30s in queue)
    rating-tolerance-increase: 50
```

**How It Works:**
```
Initial Match Attempt (0-30s):
  Player A (1500) can match with players 1300-1700

After 30 seconds:
  Player A (1500) can match with players 1250-1750

After 60 seconds:
  Player A (1500) can match with players 1200-1800

Eventually matches anyone if queue too long
```

### ELO Rewards & Bonuses

**Win Streak Bonus:**
```yaml
elo-system:
  rewards:
    win-streak-bonus:
      enabled: true
      bonus-per-win: 2  # +2 ELO per consecutive win (max 5 streak)
```

**New Player Protection:**
```yaml
elo-system:
  rewards:
    new-player-protection:
      enabled: true
      loss-reduction: 0.5  # 50% reduced ELO loss for first 10 games
```

### ELO Ranks

Visual representation of skill levels:

| ELO Range | Rank | Color |
|-----------|------|-------|
| 0-799 | Bronze | <span style="color:#CD7F32">🥉</span> |
| 800-999 | Silver | <span style="color:#C0C0C0">🥈</span> |
| 1000-1199 | Gold | <span style="color:#FFD700">🥇</span> |
| 1200-1399 | Platinum | <span style="color:#E5E4E2">💎</span> |
| 1400-1599 | Diamond | <span style="color:#B9F2FF">💎</span> |
| 1600-1799 | Master | <span style="color:#9F2B68">👑</span> |
| 1800-1999 | Grandmaster | <span style="color:#FF4500">👑</span> |
| 2000+ | Legend | <span style="color:#FF0000">⭐</span> |

### Cross-Server ELO Sync

Sync ELO ratings across network servers.

```yaml
elo-system:
  # Enable cross-server ELO sync
  cross-server-sync: true
  
  # Sync interval (seconds)
  sync-interval: 60
```

**Benefits:**
- Consistent rating across all servers
- Network-wide leaderboards
- Fair matchmaking regardless of server

### Viewing ELO

**Your ELO:**
```bash
/duel stats

# Shows ELO rating and rank
```

**Leaderboard:**
```bash
/duel leaderboard elo
```

### ELO Best Practices

**For Competitive Servers:**
- Enable ELO matchmaking
- Use KITS mode for fairness
- Enable win streak bonuses
- Set appropriate K-factor (32 recommended)

**For Casual Servers:**
- Disable ELO or make it informational only
- Higher K-factor for faster changes
- Enable new player protection

---

## 🖥️ GUI System

Beautiful, interactive menus with MiniMessage formatting and hex colors.

### Main Menu

**Opening Main Menu:**
```bash
/duel
```

**Menu Contents:**
- **Challenge Player** - Opens player selection
- **Join Queue** - Joins matchmaking
- **Custom Kits** - Manage your kits
- **Statistics** - View your stats
- **Settings** - Configure preferences
- **Help** - Command help

### Player Selection GUI

Choose a player to challenge.

**Features:**
- Shows all online players
- Cross-server player list (if Redis enabled)
- Player heads with hover info
- Search functionality
- Pagination for many players

**Player Info Shown:**
- Username
- Current server
- Current status (in duel, in queue, available)
- Win/Loss record
- Current win streak

### Kit Selection GUI

Choose which kit to use for the duel.

**Available Kits:**
- Predefined kits (Default, UHC, NoDebuff, etc.)
- Your custom kits
- Published community kits
- Kit preview on hover

**Kit Information:**
- Kit name and icon
- Creator (for custom/published kits)
- Usage count
- Preview of items

### Kit Management GUI

Create, edit, delete, and publish kits.

**Options:**
- **Create Kit** - Save current inventory as kit
- **Delete Kit** - Remove your kit
- **Publish Kit** - Share with others
- **Unpublish Kit** - Make private again
- **Rename Kit** - Change kit name
- **View Details** - See full kit contents

### Kit Browser GUI

Browse and use kits published by other players.

**Features:**
- Search kits by name
- Sort by popularity
- Sort by creator
- Preview kit contents
- Use kit directly in duels

### Settings GUI

Configure your duel preferences.

**Available Settings:**
- **GUI Popups** - Enable/disable duel request GUIs
- **Duel Requests** - Accept all, friends only, or disabled
- **Spectators** - Allow others to spectate your duels
- **Statistics** - Public or private
- **Right-Click Challenge** - Enable/disable

### Arena Selection GUI

Choose specific arena for queue or challenge.

**Arena Information:**
- Arena name
- Current status (Available, In Use)
- Arena size
- World name
- Preview image (if configured)

### GUI Customization

Full GUI customization in `gui.yml`:

```yaml
main-menu:
  title: "<white>Duel Menu"
  size: 27  # Inventory size (9, 18, 27, 36, 45, 54)
  
  # Filler items for decoration
  filler-slots: [0, 1, 2, 3, 4, 5, 6, 7, 8]
  
  items:
    challenge-player:
      slot: 10
      material: "DIAMOND_SWORD"
      name: "<white>Challenge Player"
      lore:
        - "<gray>Challenge another player to a duel"
        - ""
        - "<gold>▸ <white>Click to select player"
      action: "open_player_selection"
```

### GUI Sounds

Customize sounds for GUI interactions.

```yaml
gui-sounds:
  open: "BLOCK_CHEST_OPEN:1.0:1.0"
  click: "UI_BUTTON_CLICK:1.0:1.2"
  back: "BLOCK_WOODEN_DOOR_CLOSE:1.0:1.0"
  error: "BLOCK_ANVIL_LAND:1.0:1.5"
```

### Common Items

Reusable GUI elements:

```yaml
common-items:
  back-button:
    material: "BARRIER"
    name: "<red>Back"
    lore:
      - "<gray>│ Return to previous menu"
    action: "go_back"
  
  next-page:
    material: "ARROW"
    name: "<gray>Next Page"
    action: "next_page"
  
  previous-page:
    material: "ARROW"
    name: "<gray>Previous Page"
    action: "previous_page"
```

---

## 📊 Scoreboard Configuration

Dynamic scoreboards for lobby, duels, and spectating.

### Lobby Scoreboard

Displayed when player is in lobby/hub.

**Default Design:**
```yaml
lobby:
  enabled: true
  title: '<gradient:#FFD700:#FFA500>⚔ DUEL ⚔</gradient>'
  lines:
    - '<gradient:#FFD700:#FFA500>━━━━━━━━━━━━━━━</gradient>'
    - ''
    - '<gradient:#FFFFFF:#FFFF00>▸ SERVER</gradient>'
    - '<gray>│ Online<dark_gray>: <green><online>'
    - '<gray>│ Mode<dark_gray>: <yellow><mode>'
    - '<gray>│ Ping<dark_gray>: <white><player_ping>ms'
    - ''
    - '<gradient:#FFFFFF:#FFFF00>▸ STATS</gradient>'
    - '<gray>│ <green>W <white><wins> <dark_gray>│ <red>L <white><losses>'
    - '<gray>│ W/L<dark_gray>: <white><wlr>'
    - '<gray>│ Rate<dark_gray>: <white><win_rate>%'
    - '<gray>│ Streak<dark_gray>: <white><win_streak>'
    - ''
    - '<gradient:#FFD700:#FFA500>play.yourserver.com</gradient>'
```

### In-Duel Scoreboard

Displayed during active duels.

**Default Design:**
```yaml
in-duel:
  enabled: true
  title: '<gradient:#FF4444:#FF8888><bold>⚔ DUEL ⚔</bold></gradient>'
  lines:
    - '<gradient:#FF0000:#FF6600>━━━━━━━━━━━━━━━</gradient>'
    - ''
    - '<gradient:#FFAA00:#FFDD00>MATCH</gradient>'
    - '<gray>Arena<dark_gray>: <yellow><arena>'
    - '<gray>Kit<dark_gray>: <green><kit>'
    - '<gray>Time<dark_gray>: <gold><match_time>'
    - ''
    - '<gradient:#FF4444:#FF8888>OPPONENT</gradient>'
    - '<gray>Name<dark_gray>: <red><opponent_name>'
    - '<gray>Ping<dark_gray>: <white><opponent_ping>ms'
    - '<gray>Health<dark_gray>: <white><opponent_health>'
    - ''
    - '<gradient:#00FF00:#00FFFF>YOUR STATS</gradient>'
    - '<gray>W/L<dark_gray>: <white><wlr>'
    - '<gray>ELO<dark_gray>: <gold><elo>'
```

### Spectator Scoreboard

Displayed when spectating a duel.

```yaml
spectating:
  enabled: true
  title: '<gradient:#9B59B6:#E74C3C>SPECTATING</gradient>'
  lines:
    - '<gradient:#9B59B6:#E74C3C>━━━━━━━━━━━━━━━</gradient>'
    - ''
    - '<white><bold>MATCH INFO</bold>'
    - '<gray>Arena<dark_gray>: <yellow><arena>'
    - '<gray>Time<dark_gray>: <gold><match_time>'
    - ''
    - '<red><bold><player1_name></bold>'
    - '<gray>Health<dark_gray>: <white><player1_health>'
    - '<gray>Ping<dark_gray>: <white><player1_ping>ms'
    - ''
    - '<green><bold><player2_name></bold>'
    - '<gray>Health<dark_gray>: <white><player2_health>'
    - '<gray>Ping<dark_gray>: <white><player2_ping>ms'
```

### Scoreboard Placeholders

Available placeholders for scoreboards:

**General:**
- `<online>` - Online players
- `<mode>` - Current duel mode
- `<player_ping>` - Your ping
- `<player_name>` - Your username

**Statistics:**
- `<wins>` - Your wins
- `<losses>` - Your losses
- `<wlr>` - Win/Loss ratio
- `<win_rate>` - Win rate percentage
- `<win_streak>` - Current win streak
- `<best_streak>` - Best win streak
- `<kills>` - Total kills
- `<deaths>` - Total deaths
- `<kdr>` - Kill/Death ratio
- `<elo>` - ELO rating

**Match-Specific:**
- `<arena>` - Current arena name
- `<kit>` - Current kit name
- `<match_time>` - Time remaining
- `<opponent_name>` - Opponent username
- `<opponent_ping>` - Opponent ping
- `<opponent_health>` - Opponent health
- `<opponent_wins>` - Opponent wins
- `<opponent_losses>` - Opponent losses

**Spectating:**
- `<player1_name>` - Player 1 username
- `<player1_health>` - Player 1 health
- `<player1_ping>` - Player 1 ping
- `<player2_name>` - Player 2 username
- `<player2_health>` - Player 2 health
- `<player2_ping>` - Player 2 ping

### Scoreboard Update Intervals

Configure how often scoreboards update:

```yaml
scoreboard:
  enabled: true
  
  lobby:
    enabled: true
    update-interval: 40  # ticks (2 seconds)
  
  duel:
    enabled: true
    update-interval: 20  # ticks (1 second)
  
  countdown:
    enabled: true
    update-interval: 20  # ticks (1 second)
```

---

## 🔌 PlaceholderAPI Integration

Use JustDuel data in other plugins via PlaceholderAPI.

### Installation

1. Install [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/)
2. Install JustDuel
3. Restart server
4. Expansion auto-registers

### Player Statistics Placeholders

**Wins & Losses:**
```
%justduel_wins%           # Total wins
%justduel_losses%         # Total losses
%justduel_wlr%            # Win/Loss ratio (formatted)
%justduel_wlr_raw%        # Win/Loss ratio (decimal)
%justduel_win_rate%       # Win rate percentage
```

**Kills & Deaths:**
```
%justduel_kills%          # Total kills
%justduel_deaths%         # Total deaths
%justduel_kdr%            # Kill/Death ratio (formatted)
%justduel_kdr_raw%        # Kill/Death ratio (decimal)
```

**Streaks:**
```
%justduel_win_streak%     # Current win streak
%justduel_best_streak%    # Best win streak ever
%justduel_lose_streak%    # Current lose streak
```

**Activity:**
```
%justduel_total_duels%    # Total duels played
%justduel_last_duel%      # Time since last duel
```

**Status:**
```
%justduel_in_duel%        # true/false if in duel
%justduel_in_queue%       # true/false if in queue
%justduel_duel_mode%      # Current duel mode
```

**ELO:**
```
%justduel_elo%            # Current ELO rating
%justduel_elo_rank%       # ELO rank name
%justduel_elo_color%      # ELO rank color
```

### Leaderboard Placeholders

**Top Wins:**
```
%justduel_top_wins_1_name%    # #1 player name
%justduel_top_wins_1_value%   # #1 player wins
%justduel_top_wins_2_name%    # #2 player name
%justduel_top_wins_2_value%   # #2 player wins
...
%justduel_top_wins_10_name%   # #10 player name
%justduel_top_wins_10_value%  # #10 player wins
```

**Top Kills:**
```
%justduel_top_kills_1_name%
%justduel_top_kills_1_value%
...
```

**Top K/D Ratio:**
```
%justduel_top_kdr_1_name%
%justduel_top_kdr_1_value%
...
```

**Top ELO:**
```
%justduel_top_elo_1_name%
%justduel_top_elo_1_value%
...
```

### Usage Examples

**Scoreboard (with DeluxeScoreboard):**
```yaml
lines:
  - "&6&lYOUR STATS"
  - "&fWins: &a%justduel_wins%"
  - "&fLosses: &c%justduel_losses%"
  - "&fW/L: &e%justduel_wlr%"
  - "&fStreak: &b%justduel_win_streak%"
  - ""
  - "&6&lLEADERBOARD"
  - "&71. &f%justduel_top_wins_1_name% &7- &a%justduel_top_wins_1_value%"
  - "&72. &f%justduel_top_wins_2_name% &7- &a%justduel_top_wins_2_value%"
  - "&73. &f%justduel_top_wins_3_name% &7- &a%justduel_top_wins_3_value%"
```

**Chat Format (with EssentialsXChat):**
```yaml
format: '<{DISPLAYNAME}> {MESSAGE}'
DISPLAYNAME: '&f%player_name% &7[&e%justduel_elo%&7]'
```

**Holograms (with DecentHolograms):**
```yaml
lines:
  - '&6&lTOP DUELISTS'
  - '&71. &f%justduel_top_wins_1_name% &7- &a%justduel_top_wins_1_value% wins'
  - '&72. &f%justduel_top_wins_2_name% &7- &a%justduel_top_wins_2_value% wins'
  - '&73. &f%justduel_top_wins_3_name% &7- &a%justduel_top_wins_3_value% wins'
```

**Tab List (with TAB):**
```yaml
tablist-name: '&f%player_name% &7[&e%justduel_elo%&7]'
```

---

## 🚀 Performance Optimization

JustDuel is optimized to support **200+ concurrent players** with minimal server impact.

### Performance Features

#### Memory Management
```
✅ SoftReference caching for ItemStacks
✅ ConcurrentHashMap for thread-safe collections
✅ Automatic cache invalidation
✅ Memory-efficient GUI system
✅ Lazy loading of player data
✅ Weak references for temporary data
```

#### Database Optimization
```
✅ HikariCP connection pooling
✅ Async database operations
✅ Batch stat updates (20-tick intervals)
✅ Prepared statements (SQL injection safe)
✅ Connection health monitoring
✅ Auto-reconnect on failure
✅ Query result caching
```

#### Thread Safety
```
✅ ConcurrentHashMap for all shared data
✅ AtomicLong for counters
✅ Synchronized methods where needed
✅ Bukkit/Folia scheduler awareness
✅ Region-aware scheduling (Folia)
✅ No blocking operations on main thread
```

#### Redis Optimization
```
✅ Connection pooling (Jedis)
✅ Pipeline operations for batching
✅ Pub/Sub for real-time events
✅ TTL for auto-cleanup
✅ Circuit breaker pattern
✅ Retry logic with backoff
```

### Performance Monitoring

Built-in performance monitoring tracks:

```yaml
performance:
  monitoring:
    # Warn when entity count exceeds threshold
    max-entities-per-world: 1000
    
    # Warn when chunk count exceeds threshold
    max-chunks-per-world: 1200
    
    # Enable automatic memory optimization
    auto-memory-optimization: true
```

### Logging Rate Limiting

Prevent log spam with intelligent rate limiting:

```yaml
performance:
  logging:
    # Rate limit damage cancellation debug messages (ms)
    damage-cancel-log-cooldown: 5000
    
    # Rate limit scoreboard update debug messages (ms)
    scoreboard-update-log-cooldown: 10000
    
    # Rate limit cross-server sync debug messages (ms)
    cross-server-sync-log-cooldown: 30000
```

### Expected Performance

**Test Environment:**
- Server: Paper 1.21
- Players: 200 concurrent
- Duels: 50 simultaneous
- Hardware: 4 vCPU, 8GB RAM

**Results:**

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| **TPS** | >19.0 | 19.8 | ✅ |
| **Memory** | <1GB | ~700MB | ✅ |
| **DB Queries** | <50ms | 15-25ms | ✅ |
| **GUI Open** | <100ms | 20-40ms | ✅ |
| **Death Respawn** | <1ms | <1ms | ✅ |
| **Redis Ops** | <10ms | 2-5ms | ✅ |
| **Match Start** | <500ms | 200-300ms | ✅ |

### Optimization Tips

**For High-Population Servers:**
```yaml
# Reduce update intervals
scoreboard:
  lobby:
    update-interval: 60  # 3 seconds (default: 40)
  duel:
    update-interval: 40  # 2 seconds (default: 20)

# Increase sync intervals
cross-server:
  mysql:
    stats-sync-interval: 120  # 2 minutes (default: 60)
```

**For Low-Resource Servers:**
```yaml
# Disable features you don't need
scoreboard:
  enabled: false  # Disable scoreboards

elo-system:
  enabled: false  # Disable ELO if not needed

# Reduce database connections
storage:
  mysql:
    pool:
      maximum-pool-size: 5  # Lower (default: 10)
```

**For Networks:**
```yaml
# Optimize Redis
redis:
  connection-pool:
    max-total: 32  # Increase for high load
    max-idle: 16
    min-idle: 8

# Batch operations
cross-server:
  mysql:
    sync-interval: 30  # More frequent syncing
```

### World Management

Automatic world loading/unloading saves resources:

```yaml
world-management:
  # Automatically unload unused arena worlds
  unload-unused-worlds: true
  
  # Time before unloading (minutes)
  unload-delay-minutes: 10
  
  # Keep spawn chunks loaded
  keep-spawn-loaded: false
  
  # Max concurrent world loads
  max-concurrent-loads: 3
  
  # Pre-load all arenas on startup
  preload-worlds: false
```

---

## ⚙️ Configuration Guide

Comprehensive guide to all configuration files and options.

### Configuration Files

| File | Purpose | Reloadable |
|------|---------|------------|
| `config.yml` | Main settings, modes, features | ✅ Yes |
| `messages.yml` | All text output and formatting | ✅ Yes |
| `arenas.yml` | Arena definitions and locations | ✅ Yes |
| `kits.yml` | Predefined kit configurations | ✅ Yes |
| `gui.yml` | GUI layouts and designs | ✅ Yes |
| `scoreboard.yml` | Scoreboard configurations | ✅ Yes |
| `queue.yml` | Queue system settings | ✅ Yes |

### Reloading Configuration

**Reload All Files:**
```bash
/da system reload
```

**Reload Specific Files:**
```bash
/da system reloadconfig    # config.yml only
/da system reloadmessages  # messages.yml only
```

### config.yml Overview

**Structure:**
```yaml
# License & Server Identity
license-key: 'YOUR_KEY'
server-name: 'server1'

# Proxy Settings
proxy-settings:
  proxy-type: NONE  # NONE, BUNGEE, VELOCITY

# Storage
storage:
  type: sqlite  # sqlite, mysql, mariadb

# Redis
redis:
  enabled: false

# Core Gameplay
duel-mode: KITS  # KITS, SMP, SMP-HARD
countdown-seconds: 5
request-timeout-seconds: 60

# Wagering
wagering:
  enabled: false
  min-wager: 100.0
  max-wager: 10000.0

# Server Restrictions
server-restrictions:
  enabled: true
  restrict-modes:
    KITS: false
    SMP: false
    SMP-HARD: true

# ELO System
elo-system:
  enabled: false
  starting-rating: 1200

# Cross-Server
cross-server:
  primary-method: 'mysql'

# Performance
performance:
  logging:
    damage-cancel-log-cooldown: 5000
  monitoring:
    max-entities-per-world: 1000

# World Control
world-control:
  disable-weather-change: true
  lock-time-to-day: true
  disable-mob-spawning: true
```

### messages.yml Overview

All plugin messages with MiniMessage formatting:

```yaml
# Prefixes
prefix: '<#00A8FF>[<bold>Duel</bold>]</#00A8FF>'

# Duel Messages
duel:
  request-sent: '<prefix> <green>Duel request sent to <white><player>'
  request-received: '<prefix> <player> wants to duel you!'
  accepted: '<prefix> <green>Duel accepted!'
  
# Error Messages
errors:
  no-permission: '<prefix> <red>You don''t have permission!'
  player-not-found: '<prefix> <red>Player not found!'
  already-in-duel: '<prefix> <red>That player is already in a duel!'
  
# Success Messages
success:
  arena-created: '<prefix> <green>Arena created successfully!'
  kit-saved: '<prefix> <green>Kit saved!'
```

### GUI Customization

**Customizing GUI Items:**
```yaml
main-menu:
  items:
    challenge-player:
      slot: 10
      material: "DIAMOND_SWORD"
      name: "<white>Challenge Player"
      lore:
        - "<gray>Challenge another player"
        - ""
        - "<gold>▸ <white>Click to open"
      action: "open_player_selection"
      
      # Optional: Custom model data
      custom-model-data: 1
      
      # Optional: Enchant glow
      enchanted: true
```

### Arena Configuration

**Manual Arena Editing:**
```yaml
# arenas.yml
arenas:
  my-arena:
    name: "My Arena"
    world: "world"
    enabled: true
    
    # Boundaries
    pos1: {x: 100, y: 64, z: 100}
    pos2: {x: 150, y: 100, z: 150}
    
    # Spawn points
    spawn1:
      x: 110.5
      y: 65.0
      z: 110.5
      yaw: 90.0
      pitch: 0.0
    
    spawn2:
      x: 140.5
      y: 65.0
      z: 140.5
      yaw: -90.0
      pitch: 0.0
```

### Kit Configuration

**Editing Kits:**
```yaml
# kits.yml
kits:
  my-kit:
    queue-show: true  # Show in queue selection
    display-item: DIAMOND_SWORD  # Icon in GUI
    
    inventory:
      # Items use Bukkit serialization
      - ==: org.bukkit.inventory.ItemStack
        v: 3938
        type: DIAMOND_SWORD
    
    armor:
      - ==: org.bukkit.inventory.ItemStack
        v: 3938
        type: DIAMOND_BOOTS
```

**Note:** Easier to create kits in-game with `/duel kit create`

### Scoreboard Customization

**Custom Scoreboard:**
```yaml
lobby:
  enabled: true
  title: '<gradient:#FFD700:#FFA500>MY SERVER</gradient>'
  lines:
    - ''
    - '<white>Player: <gold><player_name>'
    - '<white>Wins: <green><wins>'
    - '<white>Losses: <red><losses>'
    - ''
    - '<gray>IP: play.myserver.com'
```

### Advanced Configuration

**Match Timer Settings:**
```yaml
match-timer:
  enabled: true
  duration-seconds: 300  # 5 minutes
  
  sudden-death:
    damage-interval-ticks: 40  # 2 seconds
    damage-amount: 2.0  # 1 heart
```

**Player Interaction:**
```yaml
player-interaction:
  # Right-click players to challenge
  right-click-to-challenge: true
  
  # Disable during duels
  disable-during-duels: true
  
  # Disable with weapon in hand
  disable-with-weapon: true
  
  # Cooldown (seconds)
  interaction-cooldown: 3
```

**Teleportation Effects:**
```yaml
teleportation:
  smooth-effects:
    enabled: true
    particles: true
    sounds: true
    teleport-sound: "ENTITY_ENDERMAN_TELEPORT"
    arrival-sound: "ENTITY_ENDERMAN_TELEPORT"
    volume: 1.0
    pitch: 1.0
```

---

## 🔧 Troubleshooting

### Common Issues

**Issue: Death screen appears after duel death**
- **Status**: ✅ FIXED in v4.0.0
- **Solution**: Instant spectator mode on death

**Issue: Duplicate holograms appearing**
- **Status**: ✅ FIXED in v4.0.0
- **Solution**: Run `/da system cleanup` to remove duplicates

**Issue: Cross-server wagering blocked**
- **Status**: ✅ INTENDED - Server restriction feature
- **Reason**: Prevents unfair economy differences
- **Solution**: Disable in config if single-server or unified economy

**Issue: SMP-HARD mode blocked for cross-server**
- **Status**: ✅ INTENDED - Server restriction feature
- **Reason**: Prevents item loss in different economies
- **Solution**: Use KITS or SMP mode for cross-server duels

**Issue: Stats colors showing as literal text**
- **Status**: ✅ FIXED in v4.0.0
- **Solution**: Proper hex closing tags now used

### Debug Commands

```
/da debug status        # Show plugin status
/da debug log [on|off]  # Toggle debug logging
/da debug diagnose      # Run diagnostics
/da debug checkarenas   # Validate all arenas
```

---

## 📋 Permissions

### Player Permissions

| Permission | Description | Default |
|------------|-------------|---------|
| `justduel.use` | Use basic duel commands | Everyone |
| `justduel.spectate` | Spectate ongoing duels | Everyone |
| `justduel.bypass.cooldown` | Bypass request cooldowns | OP |

### Admin Permissions

| Permission | Description | Default |
|------------|-------------|---------|
| `justduel.admin` | All admin commands | OP |
| `justduel.admin.arena` | Arena management | OP |
| `justduel.admin.server` | Server management | OP |
| `justduel.admin.system` | System commands | OP |
| `justduel.admin.debug` | Debug commands | OP |

---

## 📜 Changelog

### Version 4.0.0-DEV (November 2, 2025)

**New Features:**
- 💰 **Wagering System** - Full Vault integration for currency betting
- 🛡️ **Server Restrictions** - Prevents unfair cross-server duels
- ✅ **Python Verification** - Complete logic testing and validation

**Bug Fixes:**
- ✅ Death screen bug fixed
- ✅ Stats display color formatting corrected
- ✅ Hologram duplication prevention
- ✅ All code quality warnings resolved

**Performance:**
- ✅ Optimized for 200+ concurrent players
- ✅ Redis caching for stats (<1ms load time)
- ✅ Batch stat updates

---

## 💬 Support & Links

### Get Help
- **Discord**: [Join our server](https://discord.gg/HRjcmEYXNy)
- **Issues**: [GitHub Issues](https://github.com/kotori/justduel/issues)
- **Documentation**: [Full Wiki](https://github.com/kotori/justduel/wiki)

### Credits
- **Developer**: kotori
- **Special Thanks**: Paper team, Folia developers, Vault creators

---

## 📄 License

JustDuel is proprietary software. All rights reserved.

**License Key Required**: Enter your license key in `config.yml`:
```yaml
license-key: 'ENTER_YOUR_LICENSE_KEY_HERE'
```

---

<p align="center">
<strong>Made with ❤️ by kotori</strong><br>
</p>

<p align="center">
⭐ Star us on GitHub if you enjoy JustDuel! ⭐
</p>
