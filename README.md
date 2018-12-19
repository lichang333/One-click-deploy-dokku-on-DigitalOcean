# One-click deploy dokku on DigitalOcean

### local
git remote add dokku dokku@chiwei.fun:citygem.chiwei.fun
git push dokku master

### server side
dokku apps:create citygem

sudo dokku plugin:install https://github.com/dokku/dokku-postgres.git
dokku postgres:create city-gem-rails-api_production
dokku postgres:link city-gem-rails-api_production citygem


### Skipping deployment mode
dokku config:set citygem DOKKU_SKIP_DEPLOY=true

### Re-Deploying / restarting
dokku ps:rebuild citygem


```
=====> Application deployed:
       http://citygem.chiwei.fun

To chiwei.fun:citygem
 * [new branch]      master -> master
```
