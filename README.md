# Filelist API Whitelist

Based on [DevilRange](https://github.com/DevilRange/filelist-api-whitelist)'s work

### Docker Run:
```sh
docker run -d \
  --name filelist-api-whitelist \
  --restart unless-stopped \
  -e TZ=Europe/Bucharest \
  -e FL_USERNAME="USER" \
  -e FL_PASSWORD="PASS" \
  -e FL_CHECK_DELAY=900 \
  ghcr.io/rursache/filelist-api-whitelist:latest
```

### Docker Compose:
```yaml
version: '3.2'
services:
    filelist-api-whitelist:
      image: ghcr.io/rursache/filelist-api-whitelist:latest
      container_name: filelist-api-whitelist
      environment:
        TZ: Europe/Bucharest
        FL_USERNAME: "USER"
        FL_PASSWORD: "PASS"
        FL_CHECK_DELAY: 900
      restart: unless-stopped
```

> [!NOTE]
> `FL_CHECK_DELAY` is the delay between checks in seconds

### LICENSE
[GNU General Public License v3.0](LICENSE)
