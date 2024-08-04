# compose

[🇺🇸English Instructions🇺🇸](README.md) | [🇧🇷Instruções em Português🇧🇷](LEIAME.md) | [🇫🇷Instructions en français🇫🇷](LISEZ-MOI.md)

Questo repository contiene molti file di configurazione da utilizzare con [Docker Compose]. Ogni file contiene una configurazione di esempio per un contenitore specifico.

## Instruzione d'uso

Rinomina il contenitore che ti serve come `docker-compose.yml`, quindi eseguilo usando:

```bash
docker-compose up
```

Per l'uso in modalità background (daemon):

```bash
docker-compose up -d
```

Se hai bisogno di più contenitori nello stesso file, unisci i contenitori di cui hai bisogno in un'unico `docker-compose.yml`, durante l'unione ricordati di apportare le modifiche necessarie.

## Contenuto della confezione

* [cloudflare-tunnel](cloudflare-tunnel/docker-compose.yml) uno Cloudflare Tunnel utilizzando [cloudflare/cloudflared](https://hub.docker.com/r/cloudflare/cloudflared).
* [draw.io](draw.io/docker-compose.yml) uno [draw.io](https://draw.io) server utilizzando [jgraph/draw.io](https://hub.docker.com/r/jgraph/drawio).
* [guacamole](guacamole/docker-compose.yml) uno [Apache Guacamole](https://guacamole.apache.org/) server utilizzando [guacamole/guacamole](https://hub.docker.com/r/guacamole/guacamole).
* [homepage](homepage/docker-compose.yml) uno [Homepage](https://gethomepage.dev/latest/) server utilizzando [ghcr.io/gethomepage/homepage](https://ghcr.io/gethomepage/homepage).
* [kimai](kimai/docker-compose.yml) uno [Kimai](https://www.kimai.org/) server utilizzando [kimai/kimai2](https://hub.docker.com/r/kimai/kimai2).
* [kiwix-serve](kiwix-serve/docker-compose.yml) uno [Kiwix](https://wiki.kiwix.org/wiki/Kiwix-serve) server utilizzando [kiwix/kiwix-serve](https://github.com/kiwix/kiwix-tools/pkgs/container/kiwix-serve).
* [mongodb](mongodb/docker-compose.yml) uno [MongoDB](https://www.mongodb.com/) server utilizzando [mongo](https://hub.docker.com/_/mongo) e [mongo-express](https://hub.docker.com/_/mongo-express).
* [mysql-phpmyadmin](mysql-phpmyadmin/docker-compose.yml) uno [MySQL](https://www.mysql.com/) server e [phpMyAdmin](https://www.phpmyadmin.net/) utilizzando [mariadb](https://hub.docker.com/_/mariadb) e [phpmyadmin](https://hub.docker.com/_/phpmyadmin).
* [myst](myst/docker-compose.yml) uno [Mysterium Network](https://www.mysterium.network/) server utilizzando [mysteriumnetwork/myst](https://hub.docker.com/r/mysteriumnetwork/myst).
* [n8n](n8n/docker-compose.yml) uno [n8n](https://n8n.io/) server utilizzando [n8nio/n8n](https://hub.docker.com/r/n8nio/n8n).
* [nextcloud](nextcloud/docker-compose.yml) uno [Nextcloud](https://nextcloud.com/) server utilizzando [nextcloud](https://hub.docker.com/_/nextcloud).
* [nginx-proxy-manager](nginx-proxy-manager/docker-compose.yml) uno [Nginx Proxy Manager](https://nginxproxymanager.com/) server utilizzando [jc21/nginx-proxy-manager](https://hub.docker.com/r/jc21/nginx-proxy-manager).
* [`openvpn-server`](openvpn-server/docker-compose.yml) uno [OpenVPN] server utilizzando [kylemanna/openvpn].
* [portainer](portainer/docker-compose.yml) uno [Portainer](https://www.portainer.io/) server utilizzando [portainer/portainer-ce](https://hub.docker.com/r/portainer/portainer-ce).
* [proxy-telegram-mtproto](proxy-telegram-mtproto/docker-compose.yml) uno [Telegram MTProto Proxy](https://github.com/TelegramMessenger/MTProxy) utilizzando [telegrammessenger/proxy](https://hub.docker.com/r/telegrammessenger/proxy).
* [rustdesk-server](rustdesk-server/docker-compose.yml) uno [RustDesk](https://rustdesk.com/) server utilizzando [rustdesk/rustdesk](https://hub.docker.com/r/rustdesk/rustdesk-server).
* [`rutorrent-client`](rutorrent-client/docker-compose.yml) uno client torrent con un'interfaccia web utilizzando [bishof/torrent].
* [seafile](seafile/docker-compose.yml) uno [Seafile](https://www.seafile.com/en/home/) server utilizzando [seafileltd/seafile](https://hub.docker.com/r/seafileltd/seafile).
* [stirling-pdf](stirling-pdf/docker-compose.yml) uno [Stirling PDF](https://stirlingtools.com/) server utilizzando [frooodle/s-pdf](https://hub.docker.com/r/frooodle/s-pdf).
* [traccar](traccar/docker-compose.yml) uno [Traccar](https://www.traccar.org/) server utilizzando [traccar/traccar](https://hub.docker.com/r/traccar/traccar).
* [`unifi`](unifi/docker-compose.yml) uno Ubiquiti Unifi controller per gestione UAP utilizzando [jacobalberty/unifi].
* [uptime-kuma](uptime-kuma/docker-compose.yml) uno [Uptime Kuma](https://uptime.kuma.pet/) server utilizzando [soywiz/uptime-kuma](https://hub.docker.com/r/louislam/uptime-kuma).

[Docker Compose]: https://docs.docker.com/compose/
[OpenVPN]: https://openvpn.net/
[bishof/torrent]: https://hub.docker.com/r/bishof/torrent
[jacobalberty/unifi]: https://hub.docker.com/r/jacobalberty/unifi
[kylemanna/openvpn]: https://hub.docker.com/r/kylemanna/openvpn
