# Filelist API Whitelist
A simple script that will keep your public IP updated in your Filelist profile so you can keep accessing the API via Prowlarr.

The docker image supports `amd64`, `arm64` and `arm/v6/v7` archs

## How to run
### Python
```sh
git clone https://github.com/rursache/filelist-api-whitelist
pip install -r requirements. txt
python filelist_whitelist_ip.py -FL_USERNAME "USER" -FL_PASSWORD "PASS" -FL_CHECK_DELAY 900
```

### Docker CLI
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

### Docker Compose
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

## Acknowledgements
Based upon [DevilRange](https://github.com/DevilRange/filelist-api-whitelist) and [ihatethecloud](https://github.com/ihatethecloud/filelist-api-whitelist)'s python implementations

## LICENSE
This repo is available under the MPL-2.0 license. See the [LICENSE](LICENSE) file for more info.
