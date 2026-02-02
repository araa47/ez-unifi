# ez-unifi

**Agent-friendly UniFi Network tools.** Simple Python script for managing your UniFi network - devices, clients, WiFi, firewall, and more.

Built for AI agents with simple setup - just provide your controller credentials.

## Install

### Claude Code

```bash
# Add the marketplace
/plugin marketplace add araa47/ez-unifi

# Install the plugin
/plugin install ez-unifi@ez-unifi
```

### ClawHub

```bash
npx clawhub@latest install ez-unifi
```

### Other Agents (Cursor, Windsurf, etc.)

Copy the `ez-unifi/skills/ez-unifi` folder into your agent's skills directory.

---

## Setup

1. Create a **local admin account** on your UniFi controller:
   - Go to Settings → System → Administration
   - Click "Add Admin"
   - **Disable "Remote Access"** (keeps it local-only)
   - Set username/password

2. Add credentials to `.env`:
```bash
UNIFI_HOST=https://192.168.1.1
UNIFI_USERNAME=your_admin
UNIFI_PASSWORD=your_password
UNIFI_SITE=default
UNIFI_IS_UDM=true
```

Set `UNIFI_IS_UDM=false` for Cloud Key Gen1 or self-hosted controllers.

## Usage

```bash
# System
uv run scripts/unifi.py sites           # List sites
uv run scripts/unifi.py health          # Network health
uv run scripts/unifi.py sysinfo         # System info

# Devices
uv run scripts/unifi.py devices         # List all devices
uv run scripts/unifi.py restart MAC     # Restart device

# Clients
uv run scripts/unifi.py clients         # List connected clients
uv run scripts/unifi.py block MAC       # Block client
uv run scripts/unifi.py unblock MAC     # Unblock client

# WiFi
uv run scripts/unifi.py wlans           # List WiFi networks
uv run scripts/unifi.py wlan-enable ID  # Enable WLAN
uv run scripts/unifi.py wlan-disable ID # Disable WLAN

# Network
uv run scripts/unifi.py networks        # List networks
uv run scripts/unifi.py firewall        # List firewall rules
uv run scripts/unifi.py portforward     # List port forwards
```

Run `uv run scripts/unifi.py --help` for all commands.

## Supported Controllers

- UDM Pro / UDM SE / UDM
- Dream Machine / Dream Router
- Cloud Key Gen2+
- Self-hosted UniFi Controller

## Security

| Concern | How it's handled |
|---------|------------------|
| **Credentials** | Stored in `.env` (gitignored), never committed |
| **Connection** | Direct to your local controller, no cloud |
| **SSL** | Self-signed certs supported (common for home setups) |

---

## Issues & Contributing

Found a bug or have a feature request? Open an issue or submit a PR!

**Repository:** [github.com/YOUR_USERNAME/ez-unifi](https://github.com/YOUR_USERNAME/ez-unifi)
