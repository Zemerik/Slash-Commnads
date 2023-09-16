<h1 align = "center">Slash Commands</h1>
<p align = "center">JavaScript - V14</p>

<h2>📚Table of Contents:</h2>

- Notes - Important information to consider before you start.

- Slash Commands - An overview of what Slash Commands are.

- Benefits of Slash Commands - Highlights the advantages of using Slash Commands.

- Slash Command Handler - Detailed information on creating and using a Slash Command Handler.

- Deployment Script - Detailed information on creating and using a Deployment Script.

- Config.json - Information on creating and configuring a JSON file for your project.

- Directory Structure - Guidance on organizing your project's code into files and folders.

- Deploying Slash Commands - Step-by-step instructions for registering your commands.

- Support Resources - Where to find help if you encounter errors or have questions.

<h2>📝Notes:</h2>

This guide is intended for users of `V14`, not `V13`.
Read each section's instructions carefully before copying and pasting any code to avoid potential issues.
Take your time to understand the code by thoroughly reading each section.
If you encounter errors, it's best not to modify the code, refer to the support links in the "Support" section
or re-read the instructions.

<h2>⚔️Slash Commands:</h2>

Slash commands are commands that start with a forward slash ("/") followed by a keyword or action, similar to command-line interfaces. They offer a user-friendly way to interact with Discord bots and reduce the need for custom prefixes.

<h2>👌Benefits of Slash Commands:</h2>

- User-Friendly Interaction: Simplify user interaction with your bot by eliminating the need for complex prefixes.

- Discoverability: Discord displays a list of available slash commands when users type a forward slash, making them easy to find.

- Structured Input: Slash commands require specific parameters, reducing errors.

- Consistency: A consistent syntax improves user understanding.

- Reduced Command Conflicts: Slash commands don't conflict with other prefixes, reducing overlap.

- Server-Scoped Commands: Customize commands for different servers.

- Built-in Documentation: Discord provides built-in documentation for commands.

- Permissions: Slash commands can check user permissions for added security.

- Bot Responses: Pair slash commands with bot responses for interactivity.

- Analytics: Some libraries offer insights into command usage.

- Easier Maintenance: Slash commands simplify bot updates.

- Multi-Platform Compatibility: Work across different Discord platforms seamlessly.

<h2>📱Slash Command Handler:</h2>

> About:<br>

A Slash Command Handler, similar to a prefix Command Handler, helps manage and execute commands.

> What it does?
- Command Registration - Registers slash commands with the Discord API.
Organizes command data, such as name and description.
Facilitates easy command management and updates.

- Command Execution - Listens for user interactions triggered by slash commands.
Routes requests to the appropriate command function for execution.
Manages command execution, including responses and actions.
> Instructions:

Copy and paste the code from the `index.js` file of this repository into your project's `main entry point` (e.g., index.js or main.js).
You may be required to copy only certain parts of the code accordingly.


<h2>🏃‍♂️Deployment Script:</h2>

>About:

The Deployment Script automates the process of deploying commands:

> What it does?
- Command Registration - Defines command structure, including name and description.
Handles authentication with Discord's API securely.
- Command Deployment - Registers slash commands with Discord's API.
Supports server-specific deployment for customization.
Includes validation and error handling.
- Updating Commands - Allows updates to existing slash commands without manual deletion.

> Instructions:

- Create a file named `deploy-commands.js` and paste the code from the file [deploy-commands.js](https://github.com/Zemerik/Slash-Commnads/blob/main/deploy-commands.js)
Ensure the file is not within any subdirectories. If you are using an IDE like Visual Studio Code, then it should be sotred in the same folder as your main entry point. 

<h2>ℹ️Config.json:</h2>

> About:

A JSON file stores structured data in a human-readable format.

> Instructions:

- Create a new file in your project and name is `config.json`. Ensure that it is not in any folder or directory, if you are using an IDE like Visual Studio Code, then it should be stored in the same folder as your main entry point and deploy-commands.js. If you have a `config.json` file beforehand, kindly define `token`, `clientId`, `guildId` and skip to the next part
- Paste the code from the file [config.json](https://github.com/Zemerik/Slash-Commnads/blob/main/config.json) into the file `config.json`.
- Replace placeholders with your bot's actual token, User/Client ID, and server ID. You can get the bot token from [Dev Portal](https://discord.com/developers/applications) (you may be required to reset it). The User/Client ID can also be obtained from [Dev Portal](https://discord.com/developers/applications) or by right clicking on your bot, and selecting the option at bottom saying "Copy User Id". The Server Id of your server can be obtained by right clicking on your server, and selecting the option "Copy Server Id". 


<h2>📂Directory Structure:</h2>

> Instructions:

- Create a folder and name it `commands` in your project. .
- Within the commands folder, create subfolders as needed. You can create as many subfolders as you like and name them to your comfort. 

<h2>Commands:</h2>

> Instructions:

- Create a new file in any of your subfolders and name it the command name. After that type `.js` and hit enter. For example, if my command is `help`, then I will name the file `help.js`. 
- Slash Commands follow a certain type of code format, which you will need to use for every command. You can view the structue below or in the [ping.js](https://github.com/Zemerik/Slash-Commnads/blob/main/commands/example/ping.js) file. 

```
const { SlashCommandBuilder } = require('discord.js')
 module.exports = {
	 data: new SlashCommandBuilder()
		.setName('ping')
		.setDescription('Replies with Pong!'),
	async execute(interaction) {
		await interaction.reply('Pong!');
	},
};
```

- The Above code will reply with `Pong!` whenever someone uses the command `ping`

<h2>🏆Deploying: </h2>

> Instructions

- Each time you add, remove, or edit any of your commands, you will need to ReDeploy. To ReDeploy, head over to your shell/console and simply type the following:

```
node deploy-commands.js
```
- If you have followed the structure and there is no error with your code, it should reply with `Started Refreshing ....` and then `Sucesfully reloaded ....`. If that does not happen, please refer to the code structure in the Commands section, or refer to the links in the Support Section. 

<h2>🆘Support:</h2>

<li><a href = "https://discord.com/invite/v6QfPKCN8Y">My Discord</a></li>
<li><a href = "https://discordjs.guide/creating-your-bot/slash-commands.html#before-you-continue">Discord.js Guide</a></li>
