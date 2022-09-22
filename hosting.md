# Hosting Your Bot
[Go Back To The Main Page](./index.md)
### Heroku
**__Note: Heroku is removing its free service by November 28th 2022 so please use the other options provided as this will be removed soon__**
 
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

