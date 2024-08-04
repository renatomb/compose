# compose

[🇺🇸English Instructions🇺🇸](README.md) | [🇧🇷Instruções em Português🇧🇷](LEIAME.md) | [🇮🇹Instruzione Italiane🇮🇹](LEGGIMI.md)

Ce référentiel contient de nombreux fichiers de configuration à utiliser avec [Docker Compose]. Chaque fichier contient un exemple de configuration pour un conteneur Docker.

## Instructions d'utilisation

Renommez le conteneur dont vous avez besoin comme `docker-compose.yml`, puis exécutez-le en utilisant:

```bash
docker-compose up
```

Pour une utilisation en arrière-plan (daemon):

```bash
docker-compose up -d
```

Si vous avez besoin de plusieurs conteneurs dans le même fichier, fusionnez le contenu des fichiers dans le même fichier `docker-compose.yml`. Lors de la fusion, n'oubliez pas de d'apporter les modifications nécessaires.

## Contenu du colis

* [cloudflare-tunnel](cloudflare-tunnel/docker-compose.yml) un Cloudflare Tunnel en utilisant [cloudflare/cloudflared](https://hub.docker.com/r/cloudflare/cloudflared).
* [draw.io](draw.io/docker-compose.yml) un [draw.io](https://draw.io) serveur en utilisant [jgraph/draw.io](https://hub.docker.com/r/jgraph/drawio).
* [guacamole](guacamole/docker-compose.yml) un [Apache Guacamole](https://guacamole.apache.org/) serveur en utilisant [guacamole/guacamole](https://hub.docker.com/r/guacamole/guacamole).
* [homepage](homepage/docker-compose.yml) un [Homepage](https://gethomepage.dev/latest/) server en utilisant [ghcr.io/gethomepage/homepage](https://ghcr.io/gethomepage/homepage).
* [kimai](kimai/docker-compose.yml) un [Kimai](https://www.kimai.org/) serveur en utilisant [kimai/kimai2](https://hub.docker.com/r/kimai/kimai2).
* [kiwix-serve](kiwix-serve/docker-compose.yml) un [Kiwix](https://wiki.kiwix.org/wiki/Kiwix-serve) serveur en utilisant [kiwix/kiwix-serve](https://github.com/kiwix/kiwix-tools/pkgs/container/kiwix-serve).
* [mongodb](mongodb/docker-compose.yml) un [MongoDB](https://www.mongodb.com/) serveur en utilisant [mongo](https://hub.docker.com/_/mongo) et [mongo-express](https://hub.docker.com/_/mongo-express).
* [mysql-phpmyadmin](mysql-phpmyadmin/docker-compose.yml) un [MySQL](https://www.mysql.com/) serveur et [phpMyAdmin](https://www.phpmyadmin.net/) en utilisant [mariadb](https://hub.docker.com/_/mariadb) et [phpmyadmin](https://hub.docker.com/_/phpmyadmin).
* [myst](myst/docker-compose.yml) un [Mysterium Network](https://www.mysterium.network/) serveur en utilisant [mysteriumnetwork/myst](https://hub.docker.com/r/mysteriumnetwork/myst).
* [n8n](n8n/docker-compose.yml) un [n8n](https://n8n.io/) serveur en utilisant [n8nio/n8n](https://hub.docker.com/r/n8nio/n8n).
* [nextcloud](nextcloud/docker-compose.yml) un [Nextcloud](https://nextcloud.com/) serveur en utilisant [nextcloud](https://hub.docker.com/_/nextcloud).
* [`openvpn-serveur`](openvpn-serveur/docker-compose.yml) un [OpenVPN] serveur en utilisant [kylemanna/openvpn].
* [portainer](portainer/docker-compose.yml) un [Portainer](https://www.portainer.io/) serveur en utilisant [portainer/portainer-ce](https://hub.docker.com/r/portainer/portainer-ce).
* [proxy-telegram-mtproto](proxy-telegram-mtproto/docker-compose.yml) un [Telegram MTProto Proxy](https://github.com/TelegramMessenger/MTProxy) en utilisant [telegrammessenger/proxy](https://hub.docker.com/r/telegrammessenger/proxy).
* [rustdesk-serveur](rustdesk-serveur/docker-compose.yml) un [RustDesk](https://rustdesk.com/) serveur en utilisant [rustdesk/rustdesk](https://hub.docker.com/r/rustdesk/rustdesk-serveur).
* [`rutorrent-client`](rutorrent-client/docker-compose.yml) un client torrent avec une interface web en utilisant [bishof/torrent].
* [seafile](seafile/docker-compose.yml) un [Seafile](https://www.seafile.com/en/home/) serveur en utilisant [seafileltd/seafile](https://hub.docker.com/r/seafileltd/seafile).
* [stirling-pdf](stirling-pdf/docker-compose.yml) un [Stirling PDF](https://stirlingtools.com/) serveur en utilisant [frooodle/s-pdf](https://hub.docker.com/r/frooodle/s-pdf).
* [traccar](traccar/docker-compose.yml) un [Traccar](https://www.traccar.org/) serveur en utilisant [traccar/traccar](https://hub.docker.com/r/traccar/traccar).
* [`unifi`](unifi/docker-compose.yml) un Ubiquiti Unifi contrôleur pour la gestion UAP en utilisant [jacobalberty/unifi].
* [uptime-kuma](uptime-kuma/docker-compose.yml) un [Uptime Kuma](https://uptime.kuma.pet/) serveur en utilisant [soywiz/uptime-kuma](https://hub.docker.com/r/louislam/uptime-kuma).


[Docker Compose]: https://docs.docker.com/compose/
[OpenVPN]: https://openvpn.net/
[bishof/torrent]: https://hub.docker.com/r/bishof/torrent
[jacobalberty/unifi]: https://hub.docker.com/r/jacobalberty/unifi
[kylemanna/openvpn]: https://hub.docker.com/r/kylemanna/openvpn

