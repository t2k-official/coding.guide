# Welcome to code.github.io

This is to help you create a discord bot!

# v13 Discord Bot

```
npm install discord.js@v13.8.1

```
## Discord Developer Portal
1. Go to [Discord Developer Portal]() and login with your discord
2. Click on New Application in the top left and give your bot a name
3. On the left hand side click bot then add bot
4. On the left hand side click OAuth2 then URl Generator
5. Tick these boxes:
- bot
- application.commands
- Administrator
6. Scroll down to the bottom of the page and click copy
7. Open a new tab and paste the link you just copied and select a server for the bot to join
## Command Handler
1. Download the v13 command handler from [this link]()
2. Follow [this YouTube tutorial]()
## Creating / commands
Creating commands with the command handler is easy
```js

const { SlashCommandBuilder } = require("@discordjs/builders")

module.exports = {
    data: new SlashCommandBuilder()
        .setName("ping")
        .setDescription("Pong!"),
        async execute(interaction, client) {
           interaction.reply({ content: 'Pong!' })
    }
}
```
## Interaction
### Ephemeral
This is a bit of code make the reply only visible to the user that used the command

```js

const { SlashCommandBuilder } = require("@discordjs/builders")

module.exports = {
    data: new SlashCommandBuilder()
        .setName("ping")
        .setDescription("Pong!"),
        async execute(interaction, client) {
           interaction.reply({ content: 'Pong!', ephemeral: true })
    }
}
```
### MessageEmbed
This sends an embed message instead of a normal one
const { SlashCommandBuilder } = require("@discordjs/builders")
const { MessageEmbed } = require('discord.js')

module.exports = {
    data: new SlashCommandBuilder()
        .setName("ping")
        .setDescription("Pong!"),
        async execute(interaction, client) {
           const embed = new MessageEmbed()
           .setAuthor('Message author')
           .setTitle('Message title')
           .setDescription('Message description')
           .addFields([
               { name: 'Message field', value: 'value' }
           ])
           .setFooter('Message footer')
           .setTimestamp()

           interaction.reply({ embeds: [embed] })
    }
}
```
## Slash Commands Options
Options are useful for getting information like a channel or a role

```js

const { SlashCommandBuilder } = require("@discordjs/builders")

module.exports = {
    data: new SlashCommandBuilder()
        .setName("ping")
        .setDescription("Pong!"),
        async execute(interaction, client) {
           interaction.reply({ content: 'Pong!', ephemeral: true })
    }
}
```

## Subcommands And SubcommandGroups
## Adding A Database
## Status
## Commands Help
