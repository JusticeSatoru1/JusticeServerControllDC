# JusticeServerControllDC
# Minecraft Server Control Bot
A Discord bot designed to manage and monitor a Minecraft server. The bot allows users to start, stop, and restart the server directly from Discord. It also integrates with Ngrok and Playit.gg for server connectivity and includes an auto-shutdown feature based on player inactivity.

Features
Server Control: Start, stop, and restart the Minecraft server via Discord commands.

Player Monitoring: Track player activity and display the number of players online.

Auto-Shutdown: Automatically shuts down the server after a specified period of inactivity.

Ngrok Integration: Automatically creates a public IP for the server using Ngrok (optional).

Playit.gg Integration: Provides a public IP for the server using Playit.gg (optional).

Control Panel: A Discord message with buttons for easy server management.

# Prerequisites
Before using the bot, ensure you have the following:

Python 3.8 or higher: The bot is written in Python, so you need Python installed on your system.

Discord Bot Token: Create a bot on the Discord Developer Portal and obtain the bot token.

Minecraft Server: The bot requires a Minecraft server to manage. Ensure you have a server setup (e.g., a .bat or .sh file to start the server).

Ngrok (Optional): If you want to use Ngrok for public IPs, download and configure Ngrok.

Playit.gg (Optional): If you want to use Playit.gg for public IPs, download and configure Playit.gg.

# Installation
Clone the Repository:

bash
Copy

 Make sure to install the python : https://www.python.org/downloads/release/python-3120/

cd minecraft-server-bot
Install Dependencies:
Run the install.bat file to install the required Python packages:

bash
Copy
pip install discord.py requests
Configure the Bot:

Open the settings.txt file and fill in the required fields:

BOT_TOKEN: Your Discord bot token.

SERVER_PATH: The path to your Minecraft server's start script (e.g., run.bat).

CHANNEL_ID: The Discord channel ID where the bot will send the control panel.

NGROK_PATH (Optional): The path to the Ngrok executable if using Ngrok.

PLAYIT_PATH (Optional): The path to the Playit.gg executable if using Playit.gg.

INACTIVITY_SHUTDOWN_MINUTES: The number of minutes of inactivity before the server shuts down (default: 10 minutes).

Run the Bot:
Start the bot by running the bot.py script:

bash
Copy
python bot.py
# Usage
Once the bot is running, it will send a control panel message to the specified Discord channel. The control panel includes buttons for managing the server:

Turn ON: Starts the Minecraft server.

Turn OFF: Stops the Minecraft server (saves the world before shutting down).

Restart: Restarts the Minecraft server.

Refresh IP: Updates the server's connection information (Ngrok or Playit.gg IP).

Auto-Shutdown
If no players are online for the specified period (INACTIVITY_SHUTDOWN_MINUTES), the bot will automatically save the world and shut down the server.

Configuration Details
settings.txt File
The settings.txt file contains all the configuration options for the bot. Here's a breakdown of each setting:

Setting	Description
BOT_TOKEN	Your Discord bot token.
SERVER_PATH	Path to the Minecraft server's start script (e.g., run.bat).
NGROK_PATH	Path to the Ngrok executable (optional).
PLAYIT_PATH	Path to the Playit.gg executable (optional).
NGROK_API_KEY	Ngrok API key (optional, required for fetching Ngrok IP).
CHANNEL_ID	Discord channel ID where the bot will send the control panel.
INACTIVITY_SHUTDOWN_MINUTES	Number of minutes of inactivity before the server shuts down (default: 10).
PLAYIT_IP	Custom Playit.gg address (optional).
Troubleshooting
Bot Fails to Start:

Ensure the BOT_TOKEN is correct and the bot has the necessary permissions in your Discord server.

Make sure the Message Content Intent is enabled in the Discord Developer Portal.

Server Fails to Start:

Check the SERVER_PATH in settings.txt and ensure it points to a valid server start script.

Ensure the server files are correctly configured and the server can be started manually.

Ngrok/Playit.gg Not Working:

Ensure the paths to ngrok.exe or playit.exe are correct in settings.txt.

For Ngrok, ensure the NGROK_API_KEY is provided if using the Ngrok API.

Auto-Shutdown Not Working:

Check the INACTIVITY_SHUTDOWN_MINUTES setting in settings.txt.

Ensure the bot has permission to read the server logs.

Security Considerations
Bot Token: Never share your bot token. If the token is compromised, regenerate it immediately.

Server Paths: Ensure the paths in settings.txt are correct and point to trusted executables.

Shell Commands: The bot uses subprocess to execute shell commands. Ensure the paths and commands are validated to prevent injection attacks.

Contributing
Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

