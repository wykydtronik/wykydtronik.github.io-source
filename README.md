### kaichi.github.io

This is the source for kaichi.github.io - nothing special, just based on Hexo - an OctoPress alternative.

### Join the #Hexo IRC channel!
Find us on freenode! Signup for an IRCCloud.com account and join #Hexo on Freenode! Or try Hexchat (Windows/OSX/Linux) or Textual (OSX)

```bash
/server irc.freenode.net
/join #hexo
``` 

# Redeploying Hexo via Github Redeploying
This is a basic overview on how to redeploy the Hexo environment from source placed on Github. Assuming you've backed up your Hexo source.

## .gitignore
Before anything, remember packages.json should be added to your .gitignore - this can conflict with your other working environments. Example of my .gitignore is below.
``` bash
.DS_Store
Thumbs.db
db.json
*.log
node_modules/
public/
.deploy*/
package.json
```
## Clone A Local Copy
```bash
$ cd ~/github/
$ git clone git@github.com:kaichi/kaichi.github.io-source.git
```

## Backup .git and _config.yml to Desktop
Cut .git and _config.yml to a save place to prevent hexo init from removing / overwriting.

## Initiate Hexo
Assuming that git, node.js, and hexo are installed on your new workstation, proceed.
```bash
$ cd kaichi.github.io-source
$ hexo init
```
## Install Dependencies / Plugins
Below is examples of my setup.
``` bash
$ npm install hexo-deployer-git --save
$ npm install hexo-soundcloud -- save
```

## Copy .git and _config.yml to Hexo environment
Once the hexo environment is setup, copy the .git and _config.yml to your working enviroment. You can now use hexo generate and deploy, git add, commit, push, and pull.
