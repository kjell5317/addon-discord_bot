# Discord Bot

## Installation

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fkjell5317%2Faddon-discord_bot)

Go to the add-on store of the supervisor and click on _repositories_ under the three dots.
Copy [_https://github.com/kjell5317/addon-discord\_bot_](https://github.com/kjell5317/addon-discord_bot) into the field and add this repository.
Now you can install this add-on like any other home-assistant add-on.

## Configuration

### Bot Token

1. Visit [Discord Developer Portal](https://discord.com/developers/applications) and create an new Application!
2. Create a Discord Bot within the Application and copy the **Bot Token** to `<bot_token>`!

### MQTT

1. Make sure you have [Mosquitto broker](https://github.com/home-assistant/addons/tree/master/mosquitto) up and running!
2. Choose a unique `<topic>` which will be used by your bot to publish and subscribe!
   1. `<command>` is the topic you're **sending** _string_ commands to, which could be _mute, unmute, deaf, undeaf and kick_. All other strings that you send to this endpoint are displayed as the activity of the bot in discord.
   2. `<online>` is the topic where you're **getting** information about your _online server mebers and their activities_ as JSON.
   3. `<voice>` **returns** booleans if you're _connected to a voice channel_ and if you're muted or deafed!

### IDs

1. After you or an admin added your bot to a server you can right-click on the server name to copy the `<guild_id>` (developer mode of your account has to be enabled)
2. `<your_id>` can be found by right-clicking on your name in the users tab of the server

## How to use

1. Subscribe to your choosen `<topics>` via [HomeAssistant](https://www.home-assistant.io/integrations/sensor.mqtt/) or NodeRED
2. Publish your _commands_ to your choosen `<topic>`

You can use [this Flow](https://github.com/kjell5317/addon-discord_bot/blob/main/node-RED/flow.json) to easily use the MQTT endpoints. You need the Node-RED add-on and the [companion integration](https://github.com/zachowj/hass-node-red) installed.
Select your instances in the nodes and add your username and those of your friends you want to know about in the **EDIT**-function node.

## Customization

The Node.js server uses [Discord.js](https://discord.js.org/#/), so you can highly customize the _server.js_ file to everything you like.
