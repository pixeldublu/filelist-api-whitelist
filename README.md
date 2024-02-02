# Filelist API Whitelist

```sh
docker run -d \
  --name filelist-api-whitelist \
  --restart unless-stopped \
  -e TZ=Europe/Bucharest \
  -e FL_USERNAME="USER" \
  -e FL_PASSWORD="PASS" \
  -e FL_CHECK_DELAY=900 \
  ghcr.io/rursache/filelist-api-whitelist:master
```
