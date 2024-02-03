# Filelist API Whitelist
A simple script that will keep your public IP updated in your Filelist profile so you can keep accessing the API via Prowlarr

### Python:
```sh
git clone https://github.com/rursache/filelist-api-whitelist
pip install -r requirements. txt
python filelist_whitelist_ip.py -FL_USERNAME "USER" -FL_PASSWORD "PASS" -FL_CHECK_DELAY 900
```

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

### Acknowledgement
Based on [DevilRange](https://github.com/DevilRange/filelist-api-whitelist)'s work

### LICENSE
[GNU General Public License v3.0](LICENSE)
