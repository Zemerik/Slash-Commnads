<h1 align = "center">Slash-Commnads</h1>

<h2>What are Slash Commands?</h2>
Slash commands are a type of command that starts with a forward slash ("/") followed by a keyword or action, similar to how you might use commands in a text-based interface or a command-line interface. These commands allow you to perform various actions or interact with bots and features within Discord without needing to use a prefix like "!,"?".", or any custom prefix set by a bot. Slash commands make your bot easier to use and also reduce certain `if` statments during the development. 

<h2>Benifits of Slash Commands: </h2>
<li>User-Friendly Interaction: Slash commands provide an intuitive and user-friendly way for users to interact with your bot. Users don't need to remember and type out complex prefixes or command structures, making it easier for them to use your bot's features.</li>

<li>Discoverability: Slash commands are discoverable within Discord. When users type a forward slash ("/"), Discord displays a list of available slash commands, making it easy for users to find and use your bot's functionality.</li>

<li>Structured Input: Slash commands often require specific parameters or options, which can help ensure that users provide the correct input. This reduces the likelihood of command errors and helps your bot perform tasks accurately.</li>

<li>Consistency: Slash commands follow a consistent syntax, making it easier for users to understand how to use different bot features. This can improve the overall user experience.</li>

<li>Reduced Command Conflicts: Slash commands are distinct and don't conflict with other bot command prefixes or chat messages. This reduces the chance of command overlap or interference with other bots on the same server.</li>

<li>Server-Scoped Commands: Discord allows you to define slash commands on a per-server basis, which means your bot can have different commands for different servers. This enables customization and tailoring of your bot's functionality to suit each server's needs.</li>

<li>Built-in Documentation: Discord provides a built-in way to document and describe your bot's slash commands. Users can access information about the commands directly within Discord, enhancing user understanding.</li>

<li>Interaction with Permissions: Slash commands can be configured to check user permissions before executing certain actions. This helps ensure that only authorized users can perform specific tasks, enhancing server security.</li>

<li>Integration with Bot Responses: You can pair slash commands with bot responses to provide immediate feedback or results when a user executes a command. This creates a more interactive and responsive bot experience.</li>

<li>Analytics and Insights: Some bot development frameworks and libraries offer analytics and insights into how users are interacting with your bot's slash commands. This data can help you refine and improve your bot's functionality over time.</li>

<li>Easier Bot Maintenance: Slash commands can make bot maintenance and updates easier. You can add or modify commands without needing to update complex command handling systems or change prefixes.</li>

<li>Multi-Platform Compatibility: Slash commands work across different Discord platforms, including desktop and mobile apps, ensuring a consistent experience for users regardless of their device.</li>

<h2>Slash Command Handler: </h2>
<p>Slash Command Handler and a prefix Command Handler are a bit different, and made in different ways however there main features are almost the same.Below you can see an explanation of the code in index.js, which is the Slash Command Handler.</p>
<li>Command Registration:

One of the primary responsibilities of a Slash Command Handler is to handle the registration of slash commands with the Discord API. This includes creating and defining the commands, then sending the registration request to Discord.

It organizes command data, such as the command name, description, and any additional options or parameters, making it easier to manage and update commands.</li>

<li>Command Execution:

After registration, the Command Handler listens for incoming interactions from users in response to slash commands. When a user triggers a slash command in a Discord server where the bot is present, the Discord API sends an interaction event to the bot.

The Command Handler processes these interaction events, identifies the invoked command, and routes the request to the appropriate command function or module for execution.

It manages the execution of commands by invoking the corresponding code logic, which can include sending responses, performing actions, or providing information to users.</li>

<h2>Deployment Script</h2>
<p>The Deployment Script is a set of automated instructions that faciliate the process of deploying commands.</p>
<li>Command Registration:

The deployment script defines the structure and details of your slash commands. This includes specifying the command name, description, options, and other relevant metadata. </li>
<li>Authentication:

The script often handles authentication with Discord's API. It includes mechanisms to securely authenticate your bot with the Discord API using your bot token.</li>
<li>Command Deployment:

The main function of the script is to deploy (register) your slash commands with Discord's API. This involves making HTTP requests to Discord's API endpoints to create or update the commands on the Discord servers where your bot is active.</li>
<li>Server-Specific Deployment:

In some cases, your bot may be present on multiple Discord servers (guilds). The deployment script should have the capability to register slash commands on specific servers, allowing you to customize commands for each server if needed.</li>
<li>Validation and Error Handling:

The script should perform validation checks on the command data to ensure it adheres to Discord's requirements and constraints. It should also handle errors gracefully, providing informative messages or logs when issues arise during deployment.</li>
<li>Updating Commands:

Beyond initial deployment, the script should support updating or modifying existing slash commands. This allows you to make changes to your bot's commands without needing to manually delete and recreate them.</li>

<h2>Files & Directory: </h2>
<li>Before writing the Slash Command Handler and Deployment Script, make a file named `config.json` and enter your `bot token`, `guildId` and `clientId`. You can refer to the config.json file for any assistance, but remember to name them `token`, `guildId` and `clientId`. Ensure that your config.json is not in any folder or directory.
<li>Head over to your main file (usually called index.js/main.js) and copy paste the Slash Command Handler. The code can be obtained from the file `index.js` in this repo. Create a new file, and name it `deploy-commands.js`. Make sure that your `deploy-commands.js` file is not in any folder or directory. Add the deployment script in that file, the code can be obtained from the file `deploy-commands.js` in this repo. 
<li>After you have written your Slash Command Handler in your main file and the deployment script in another file, you need to create a folder named `commands`. In the folder that you just created, make a new subfolder, you can name it whatever you like and create as many as you want.</li>
<li>Go to any or your only subfoler, and create a new file named `ping.js`. `ping` will be the name of the command, as the name of you file before `.js` is `ping`. In there, you can add the code from the file `ping.js` in this repo.</li>
<li>Your project's directory should look like something below, ignore the files `kick.js`, `prune.js`, `avatar.js`, `reload.js`, `server.js` and `user.js`. Also note, that if you are using apps/websites like replit, then you may not even have the `node_modules` folder. </li>
<br>
<img src = "https://cdn.discordapp.com/attachments/1062477574841831594/1149286348809842708/after-sorting.png" style = "width:200px;height:400px">

<h2>Deploying: </h2>
<p>In order to register slash commands, you need to deploy your project. Your project can be deployed as many times you want and you will need to redeploy is countless times. Below is basic step by step instruction on how to deploy your slash commands. </p>

<li>Head over to your project's terminal/console, and enter `node deploy-commands.js`. If you have followed the instructions correctly, then it should display `Started refreshing 1 application (/) commands.` and then display `Successfully reloaded 1 application (/) commands.` in your console.</li>
<li>If anything other than that shows up in console, or there is some other error in the console, it is best to contact through the below links.</li>
<li>Also note, that every time you add a new commmand or edit one of your commands, you will need to do the deploying process again. Ensure that your project is not running while deploying commands as that could lead to several issues.</li>

<h2>Support: </h2>
<a href = "https://discord.gg/v6QfPKCN8Y">My Discord</a><br>
<a href = "https://discordjs.guide/creating-your-bot/slash-commands.html">Discord.js Guide</a>
