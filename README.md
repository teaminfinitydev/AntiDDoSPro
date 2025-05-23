# AntiDDoSPro

<div align="center">

![AntiDDoSPro Banner](https://i.imgur.com/placeholder.png)

[![Version](https://img.shields.io/github/v/release/teaminfinitydev/AntiDDoSPro?style=flat-square)](https://github.com/teaminfinitydev/AntiDDoSPro/releases)
[![License](https://img.shields.io/github/license/teaminfinitydev/AntiDDoSPro?style=flat-square)](LICENSE)
[![Java](https://img.shields.io/badge/Java-21-orange.svg?style=flat-square)](https://www.oracle.com/java/)
[![Paper](https://img.shields.io/badge/Paper-1.21.1-blue.svg?style=flat-square)](https://papermc.io/)

**Advanced DDoS protection for Minecraft servers**

[Features](#-features) • 
[Installation](#-installation) • 
[Commands](#-commands) • 
[Configuration](#-configuration) • 
[GeoIP Setup](#-geoip-setup) • 
[Support](#-support)

</div>

## 📋 Features

AntiDDoSPro provides comprehensive protection against Distributed Denial of Service (DDoS) attacks and connection spam for Minecraft servers:

- **Connection Rate Limiting** - Prevent connection spam from individual IP addresses
- **Advanced IP Filtering** - Whitelist trusted IPs and blacklist malicious ones
- **Country-Based Blocking** - Block connections from specific countries
- **Username Validation** - Filter out invalid or suspicious usernames
- **Auto-Blacklisting** - Automatically blacklist repeat offenders
- **Admin Notifications** - Get real-time alerts about potential attacks
- **Detailed Logging** - Track and analyze attack patterns
- **GeoIP Integration** - Identify the country of origin for connections
- **Low-Impact Performance** - Efficient design with minimal server overhead

## 💾 Installation

### Requirements
- Java 21 or newer
- Paper 1.21.1 or newer

### Steps
1. Download the latest release from the [releases page](https://github.com/teaminfinitydev/AntiDDoSPro/releases)
2. Place the JAR file in your server's `plugins` directory
3. Restart your server
4. The plugin will automatically create its configuration files and extract the GeoIP database

## 🔧 Commands

| Command | Description | Permission |
|---------|-------------|------------|
| `/antiddos reload` | Reload the configuration | `antiddos.admin` |
| `/antiddos status` | Check the plugin status | `antiddos.admin` |
| `/antiddos whitelist add <ip>` | Add an IP to the whitelist | `antiddos.admin` |
| `/antiddos whitelist remove <ip>` | Remove an IP from the whitelist | `antiddos.admin` |
| `/antiddos whitelist list` | List all whitelisted IPs | `antiddos.admin` |
| `/antiddos blacklist add <ip>` | Add an IP to the blacklist | `antiddos.admin` |
| `/antiddos blacklist remove <ip>` | Remove an IP from the blacklist | `antiddos.admin` |
| `/antiddos blacklist list` | List all blacklisted IPs | `antiddos.admin` |
| `/antiddos country add <code>` | Block a country by ISO code | `antiddos.admin` |
| `/antiddos country remove <code>` | Unblock a country | `antiddos.admin` |
| `/antiddos country list` | List all blocked countries | `antiddos.admin` |
| `/antiddos country enable` | Enable country filtering | `antiddos.admin` |
| `/antiddos country disable` | Disable country filtering | `antiddos.admin` |
| `/antiddos checkplayer <name>` | Check a player's country | `antiddos.admin` |
| `/antiddos update` | Check for plugin updates | `antiddos.admin` |

## ⚙️ Configuration

The main configuration file is located at `plugins/AntiDDoSPro/config.yml`. Here are the key settings:

### Connection Limits
```yaml
connection-limits:
  # Maximum connections from a single IP within the time window
  max-connections-per-ip: 3
  
  # Time window in seconds to track connection attempts
  time-window-seconds: 10
  
  # Temporary ban duration in minutes
  temp-ban-duration-minutes: 5
```

### Attack Detection
```yaml
detection:
  # Connection threshold that triggers rate limiting
  connection-threshold: 5
  
  # Threshold for automatic blacklisting
  auto-blacklist-threshold: 3
```

### IP Filtering
```yaml
ip-filtering:
  # Enable IP whitelisting
  enable-whitelist: false
  
  # Enable IP blacklisting
  enable-blacklist: true
```

### GeoIP Settings
```yaml
geoip:
  # Enable country-based filtering
  enable: true
  
  # List of country codes to block
  blocked-countries:
    - "RU"
    - "CN"
    - "KP"
```

### Notifications
```yaml
notifications:
  # Notify administrators when attacks are detected
  notify-admins: true
  
  # Log attack attempts to the server log
  log-attacks: true
```

## 🌎 GeoIP Setup

AntiDDoSPro comes with the GeoLite2 Country database pre-packaged, so country-based filtering works right out of the box. The database will be automatically extracted to your plugin's folder when the server starts.

### Updating the GeoIP Database

To update the GeoIP database:

1. Download the latest GeoLite2-Country.mmdb from [MaxMind](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)
2. Replace the file in `plugins/AntiDDoSPro/GeoLite2-Country.mmdb`
3. Run `/antiddos reload` to load the new database

## 📊 Screenshots

![Console Output](https://i.imgur.com/placeholder.png)
*Plugin startup message in server console*

![Command Usage](https://i.imgur.com/placeholder.png)
*Using the AntiDDoS commands in-game*

## 🔔 Support

If you encounter any issues or have questions about AntiDDoSPro:

- Submit an issue on [GitHub](https://github.com/teaminfinitydev/AntiDDoSPro/issues)
- Join our [Discord server](https://codenexa.online/developers) for direct support
- Contact the developer via email: support@codenexa.online

## 👥 Contributing

We welcome contributions to AntiDDoSPro! Here's how you can help:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

Please ensure your code follows the existing style and includes appropriate tests.

## 📄 License

AntiDDoSPro is licensed under the [MIT License](LICENSE). See the LICENSE file for details.

## 👏 Credits

- **Developed by:** Chamika Samaraweera
- **GeoIP data:** This product includes GeoLite2 data created by MaxMind, available from [https://www.maxmind.com](https://www.maxmind.com)

---

<div align="center">
  <img src="https://i.imgur.com/placeholder.png" width="100" alt="CodeNexa Logo">
  <p>Made with ❤️ by <a href="https://codenexa.online">CodeNexa</a></p>
</div>
