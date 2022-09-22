## Adding A Database
[Go Back To The Main Page](./index.md)
### quick.db
```
npm install quick.db better-sqlite3
```
[quickdb website](https://quickdb.js.org/)

Quick Db is an easy to use database using sqlite3
```js
const { QuickDB } = require('quick.db')
const db = new QuickDB
```
```js
db.add(`value_${interaction.guild.id}`, 2)
```
```js
db.delete(`value_${interaction.guild.id}`)
Or
db.delete(`value_${interaction.guild.id}`, 1)
```
```js
db.set(`value_${interaction.guild.id}`, 2)
```
