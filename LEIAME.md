# compose

[🇺🇸English Instructions🇺🇸](README.md) | [🇮🇹Instruzione Italiane🇮🇹](LEGGIMI.md) | [🇫🇷Instructions en français🇫🇷](LISEZ-MOI.md)

Este repositório contém vários arquivos de configuração para uso com o [Docker Compose]. Cada arquivo contém um modelo para um container específico.

## Instruções de uso

Renomeie o contêiner que você necessita com o nome `docker-compose.yml`, então execute usando:

```bash
docker-compose up
```

Para uso em segudo plano (daemon), use:

```bash
docker-compose up -d
```

Se você necessitar multiplos contêiners no mesmo arquivo, mescle o conteúdo dos arquivos no mesmo arquivo `docker-compose.yml`, ao mesclar faça todas as mudanças que necessitar.

## Conteúdo do pacote

* [cloudflare-tunnel](cloudflare-tunnel/docker-compose.yml) um Cloudflare Tunnel usando [cloudflare/cloudflared](https://hub.docker.com/r/cloudflare/cloudflared).
* [draw.io](draw.io/docker-compose.yml) um [draw.io](https://draw.io) server usando [jgraph/draw.io](https://hub.docker.com/r/jgraph/drawio).
* [guacamole](guacamole/docker-compose.yml) um [Apache Guacamole](https://guacamole.apache.org/) server usando [guacamole/guacamole](https://hub.docker.com/r/guacamole/guacamole).
* [homepage](homepage/docker-compose.yml) aum [Homepage](https://gethomepage.dev/latest/) server usando [ghcr.io/gethomepage/homepage](https://ghcr.io/gethomepage/homepage).
* [kimai](kimai/docker-compose.yml) um [Kimai](https://www.kimai.org/) server usando [kimai/kimai2](https://hub.docker.com/r/kimai/kimai2).
* [kiwix-serve](kiwix-serve/docker-compose.yml) um [Kiwix](https://wiki.kiwix.org/wiki/Kiwix-serve) server usando [kiwix/kiwix-serve](https://github.com/kiwix/kiwix-tools/pkgs/container/kiwix-serve).
* [MeTube](metube/docker-compose.yml) um [MeTube - interface web para com o YouTube downloader integrado](https://github.com/alexta69/metube).
* [mongodb](mongodb/docker-compose.yml) um [MongoDB](https://www.mongodb.com/) server usando [mongo](https://hub.docker.com/_/mongo) e [mongo-express](https://hub.docker.com/_/mongo-express).
* [mysql-phpmyadmin](mysql-phpmyadmin/docker-compose.yml) um [MySQL](https://www.mysql.com/) server com [phpMyAdmin](https://www.phpmyadmin.net/) usando [mariadb](https://hub.docker.com/_/mariadb) e [phpmyadmin](https://hub.docker.com/_/phpmyadmin).
* [myst](myst/docker-compose.yml) um [Mysterium Network](https://www.mysterium.network/) server usando [mysteriumnetwork/myst](https://hub.docker.com/r/mysteriumnetwork/myst).
* [n8n](n8n/docker-compose.yml) um [n8n](https://n8n.io/) server usando [n8nio/n8n](https://hub.docker.com/r/n8nio/n8n).
* [nextcloud](nextcloud/docker-compose.yml) um [Nextcloud](https://nextcloud.com/) server usando [nextcloud](https://hub.docker.com/_/nextcloud).
* [nginx-proxy-manager](nginx-proxy-manager/docker-compose.yml) um [Nginx Proxy Manager](https://nginxproxymanager.com/) server usando [jc21/nginx-proxy-manager](https://hub.docker.com/r/jc21/nginx-proxy-manager).
* [`openvpn-server`](openvpn-server/docker-compose.yml) um servidor [OpenVPN] usando [kylemanna/openvpn].
* [portainer](portainer/docker-compose.yml) um [Portainer](https://www.portainer.io/) server usando [portainer/portainer-ce](https://hub.docker.com/r/portainer/portainer-ce).
* [proxy-telegram-mtproto](proxy-telegram-mtproto/docker-compose.yml) um [Telegram MTProto Proxy](https://github.com/TelegramMessenger/MTProxy) usando [telegrammessenger/proxy](https://hub.docker.com/r/telegrammessenger/proxy).
* [rustdesk-server](rustdesk-server/docker-compose.yml) um [RustDesk](https://rustdesk.com/) server usando [rustdesk/rustdesk](https://hub.docker.com/r/rustdesk/rustdesk-server).
* [`rutorrent-client`](rutorrent-client/docker-compose.yml) um cliente torrent com interface web usando [bishof/torrent].
* [seafile](seafile/docker-compose.yml) um [Seafile](https://www.seafile.com/en/home/) server usando [seafileltd/seafile](https://hub.docker.com/r/seafileltd/seafile).
* [stirling-pdf](stirling-pdf/docker-compose.yml) um [Stirling PDF](https://stirlingtools.com/) server usando [frooodle/s-pdf](https://hub.docker.com/r/frooodle/s-pdf).
* [traccar](traccar/docker-compose.yml) um [Traccar](https://www.traccar.org/) server usando [traccar/traccar](https://hub.docker.com/r/traccar/traccar).
* [`unifi`](unifi/docker-compose.yml) um controlador Ubiquiti Unifi para gerenciamento de equipamentos UAP usando [jacobalberty/unifi].
* [uptime-kuma](uptime-kuma/docker-compose.yml) um [Uptime Kuma](https://uptime.kuma.pet/) server usando [soywiz/uptime-kuma](https://hub.docker.com/r/louislam/uptime-kuma).

[Docker Compose]: https://docs.docker.com/compose/
[OpenVPN]: https://openvpn.net/
[bishof/torrent]: https://hub.docker.com/r/bishof/torrent
[jacobalberty/unifi]: https://hub.docker.com/r/jacobalberty/unifi
[kylemanna/openvpn]: https://hub.docker.com/r/kylemanna/openvpn
