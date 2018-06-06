# linebot-template
template for linebot 

```
APP=linebot
DOKKU_HOST=dokku.local
MAIL=my@email.address

dokku apps:create ${APP}
dokku config:set ${APP} LINE_CHANNEL_ACCESS_TOKEN="MY_TOKEN_PROVIDED_BY_LINE"
dokku config:set ${APP} LINE_CHANNEL_SECRET="MY_SECRET"
git remote add dokku dokku@${DOKKU_HOST}:${APP}
git push dokku master

dokku config:set --no-restart ${APP} DOKKU_LETSENCRYPT_EMAIL=${MAIL}
dokku letsencrypt ${APP}

dokku logs ${APP} --tail
```
