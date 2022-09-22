# Hosting Your Bot
[Go Back To The Main Page](./index.md)
### Heroku
**Note: Heroku is removing its free service by November 28th 2022 so please use the other options provided as this will be removed soon**
 
Heroku is an easy to use hosting website which is completely free
Make sure your bot has a Procfile if not create one

### Procfile
1. Create a new file and name it Procfile
2. In the file type:
```js
worker: node src/index.js
```
3. Save the file

### Hosting The Bot
1. Go to [heroku](https://id.heroku.com/login)
2. Create and account or login
3. Create a new project
4. Go to the deploy option and click GitHub 
5. Login with your GitHub and then search for the bots repository you want to host
6. Enable automatic deploys then deploy and wait for it to finish
7. Go to the Dynos option and refresh the page
8. Select the worker and turn it on
9. Wait for your bot to turn on

### Daki Hosting
Daki is a free to use hosting website with a discord server to help you.

[Daki Discord Server](https://discord.gg/Y8kdErkMwk)

### How to use daki
1. Go to [daki website](https://dash.daki.cc/)
2. Log in with your discord
3. On the left hand side click create a server
4. Fill out the info that is needed
- Name of the server
- Ram = 512
- CPU = 50
- Disk = 1024
- Location = Germany (only free option)
- Pick between discord.js java or python
5. Click create server 
6. On the left hand side click credentials
7. Generate a new password and copy the password
8. Click on the word panel at the bottom of the page
9. Log in with your email for your discord and the password you copied
10. Click on the server you created then go to files
11. Upload all your files **(Not the node modules folder)**
12. Go to console and click start
13. Then wait for your bot to come online
**If there is any issues please go to the daki discord server and ask for help**
