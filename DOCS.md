# Discord Bot

## Configuration

### Bot Token

1. Visit [Discord Developer Portal](https://discord.com/developers/applications) and create an new Application!
2. Create a Discord Bot within the Application and copy the **Bot Token** to `<bot_token>`!

### MQTT

1. Make sure you have [Mosquitto broker](https://github.com/home-assistant/addons/tree/master/mosquitto) up and running!
2. Enter your `<url>` and `<login>` information!
3. Choose a unique `<topic>` which will be used by your bot to publish and subscribe!
   1. `<command>` is the topic you're **sending** _string_ commands to which could be _mute, unmute, deaf, undeaf and kick_!
   2. `<online>` is the topic where you're **getting** information about your _online server mebers and their activities_ as a json!
   3. `<voice>` **returns** a boolean if you're _connected to a voice channel_ and if you're muted or deafed!

### IDs

1. After you or an admin added your bot to a server you can right-click on the server name to copy the `<guild_id>` (developer mode of your account has to be enabled)
2. `<your_id>` can be found by right-clicking on your name in the users tab of the server!

## How to use

1. Subscribe to your choosen `<topics>` via [HomeAssistant](https://www.home-assistant.io/integrations/sensor.mqtt/) or NodeRED
2. Publish your _commands_ to your choosen `<topic>`

You can use [this Flow](https://gist.github.com/kjell5317/530394d028383119e9523e777d2ac1ce) to filter your friends and use all available commands.

## Customization

The Node.js server uses [Discord.js](https://discord.js.org/#/), so you can highly customize the _server.js_ file to everything you like.
