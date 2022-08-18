# Welcome to code.github.io

This is to help you create a discord bot!

# v13 Discord Bot

```
npm install discord.js@v13.8.1

```
## Discord Developer Portal
1. Go to [Discord Developer Portal](https://discord.com/developers/applications) and login with your discord
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
1. Download the v13 command handler from [this link](https://cdn.discordapp.com/attachments/980962737926574083/982047171832594462/SlashCommand_Package_Discord.jsv13.zip)
2. Follow [this YouTube tutorial](https://www.youtube.com/watch?v=qceocw4kf7c)
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
```js
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
        .setName("options")
        .setDescription("Slash command options!")
        .addStringOption(option => option.setName('input').setDescription('Enter a string'))
	.addIntegerOption(option => option.setName('int').setDescription('Enter an integer'))
	.addBooleanOption(option => option.setName('choice').setDescription('Select a boolean'))
	.addUserOption(option => option.setName('target').setDescription('Select a user'))
	.addChannelOption(option => option.setName('destination').setDescription('Select a channel'))
	.addRoleOption(option => option.setName('muted').setDescription('Select a role'))
	.addNumberOption(option => option.setName('num').setDescription('Enter a number'))
	.addMentionableOption(option => option.setName('mentionable').setDescription('Mention something'))
	.addAttachmentOption(option => option.setName('attachment').setDescription('Attach something')),
        async execute(interaction, client) {
           const string = interaction.options.getString('input')
           const integer = interaction.options.getInteger('int')
           const boolean = interaction.options.getBoolean('choice')
           const user = interaction.options.getUser('target')
           const member = interaction.options.getMember('target')
           const channel = interaction.options.getChannel('destination')
           const role = interaction.options.getRole('muted')
           const number = interaction.options.getNumber('num')
           const mentionable = interaction.options.getMentionable('mentionable')
           const attachment = interaction.options.getAttachment('attachment')

console.log({ string, integer, boolean, user, member, channel, role, mentionable, attachment, number });
    }
}
```
### Subcommands
Subcommands are useful for organising commands and making the commands look nicer
```js
const { SlashCommandBuilder } = require("@discordjs/builders")

module.exports = {
    data: new SlashCommandBuilder()
        .setName("subcommands")
        .setDescription("Slash command subcommands!")
        .addSubcommand(subcommand => subcommand.setName('sub').setDescription('A subcommand')),
        async execute(interaction, client) {
          if(interaction.options.getSubcommand() === 'sub') {
              console.log('subcommand')
          }
      }
}
```
### SubcommandGroups
SubcommandGroups are useful to make the subcommands look nicer
```js
const { SlashCommandBuilder } = require("@discordjs/builders")

module.exports = {
    data: new SlashCommandBuilder()
        .setName("subcommands")
        .setDescription("Slash command subcommands!")
        .addSubcommandGroup(subcommand => subcommand.setName('group').setDescription('a subcommand group').addSubcommand(subcommand => subcommand.setName('sub').setDescription('A subcommand'))),
        async execute(interaction, client) {
          if(interaction.options.getSubcommand() === 'sub') {
              console.log('subcommand group')
          }
      }
}
```

## Adding A Database
### quick.db
```
npm install quick.db
```
Go to the [quickdb website](https://quickdb.js.org/)
## Hosting The Bot
### Heroku
