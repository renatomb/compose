# compose

[🇧🇷Instruções em Português🇧🇷](LEIAME.md) | [🇮🇹Instruzione Italiane🇮🇹](LEGGIMI.md) | [🇫🇷Instructions en français🇫🇷](LISEZ-MOI.md)

This repository contains many config files for use with [Docker Compose]. Each file contains a sample config for a docker container.

## Usage Instructions

Rename the container that you need as `docker-compose.yml`, then run it using:

```bash
docker-compose up
```

For daemon mode, use:

```bash
docker-compose up -d
```

If you need multiple containers in the same file, merge the containers you need in a single `docker-compose.yml`, when merging remember to make any necessary changes.

## Package contents

* [cloudflare-tunnel](cloudflare-tunnel/docker-compose.yml) a Cloudflare Tunnel using [cloudflare/cloudflared](https://hub.docker.com/r/cloudflare/cloudflared).
* [draw.io](draw.io/docker-compose.yml) a [draw.io](https://draw.io) server using [jgraph/draw.io](https://hub.docker.com/r/jgraph/drawio).
* [guacamole](guacamole/docker-compose.yml) an [Apache Guacamole](https://guacamole.apache.org/) server using [guacamole/guacamole](https://hub.docker.com/r/guacamole/guacamole).
* [kimai](kimai/docker-compose.yml) a [Kimai](https://www.kimai.org/) server using [kimai/kimai2](https://hub.docker.com/r/kimai/kimai2).
* [kiwix-serve](kiwix-serve/docker-compose.yml) a [Kiwix](https://wiki.kiwix.org/wiki/Kiwix-serve) server using [kiwix/kiwix-serve](https://github.com/kiwix/kiwix-tools/pkgs/container/kiwix-serve).
* [mongodb](mongodb/docker-compose.yml) a [MongoDB](https://www.mongodb.com/) server using [mongo](https://hub.docker.com/_/mongo) and [mongo-express](https://hub.docker.com/_/mongo-express).
* [mysql-phpmyadmin](mysql-phpmyadmin/docker-compose.yml) a [MySQL](https://www.mysql.com/) server with [phpMyAdmin](https://www.phpmyadmin.net/) using [mariadb](https://hub.docker.com/_/mariadb) and [phpmyadmin](https://hub.docker.com/_/phpmyadmin).
* [myst](myst/docker-compose.yml) a [Mysterium Network](https://www.mysterium.network/) server using [mysteriumnetwork/myst](https://hub.docker.com/r/mysteriumnetwork/myst).
* [n8n](n8n/docker-compose.yml) a [n8n](https://n8n.io/) server using [n8nio/n8n](https://hub.docker.com/r/n8nio/n8n).
* [nextcloud](nextcloud/docker-compose.yml) a [Nextcloud](https://nextcloud.com/) server using [nextcloud](https://hub.docker.com/_/nextcloud).
* [`openvpn-server`](openvpn-server/docker-compose.yml) an [OpenVPN] server using [kylemanna/openvpn].
* [portainer](portainer/docker-compose.yml) a [Portainer](https://www.portainer.io/) server using [portainer/portainer-ce](https://hub.docker.com/r/portainer/portainer-ce).
* [proxy-telegram-mtproto](proxy-telegram-mtproto/docker-compose.yml) a [Telegram MTProto Proxy](https://github.com/TelegramMessenger/MTProxy) using [telegrammessenger/proxy](https://hub.docker.com/r/telegrammessenger/proxy).
* [rustdesk-server](rustdesk-server/docker-compose.yml) a [RustDesk](https://rustdesk.com/) server using [rustdesk/rustdesk](https://hub.docker.com/r/rustdesk/rustdesk-server).
* [rutorrent-client](rutorrent-client/docker-compose.yml) a torrent client with web interface using [bishof/torrent].
* [seafile](seafile/docker-compose.yml) a [Seafile](https://www.seafile.com/en/home/) server using [seafileltd/seafile](https://hub.docker.com/r/seafileltd/seafile).
* [stirling-pdf](stirling-pdf/docker-compose.yml) a [Stirling PDF](https://stirlingtools.com/) server using [frooodle/s-pdf](https://hub.docker.com/r/frooodle/s-pdf).
* [traccar](traccar/docker-compose.yml) a [Traccar](https://www.traccar.org/) server using [traccar/traccar](https://hub.docker.com/r/traccar/traccar).
* [`unifi`](unifi/docker-compose.yml) an Ubiquiti Unifi controller for UAP management using [jacobalberty/unifi].
* [uptime-kuma](uptime-kuma/docker-compose.yml) an [Uptime Kuma](https://uptime.kuma.pet/) server using [soywiz/uptime-kuma](https://hub.docker.com/r/louislam/uptime-kuma).


[Docker Compose]: https://docs.docker.com/compose/
[Jira ServiceDesk]: https://www.atlassian.com/software/jira/service-desk
[OpenVPN]: https://openvpn.net/
[bishof/torrent]: https://hub.docker.com/r/bishof/torrent
[jacobalberty/unifi]: https://hub.docker.com/r/jacobalberty/unifi
[kylemanna/openvpn]: https://hub.docker.com/r/kylemanna/openvpn
