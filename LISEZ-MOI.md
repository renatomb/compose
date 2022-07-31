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

Si vous avez besoin de plusieurs conteneurs dans le même fichier, fusionnez le contenu des fichiers dans le même fichier `docker-compose.yml`. Lors de la fusion, n'oubliez pas de ne conserver que la première ligne contenant `version` et d'apporter les modifications nécessaires.

## Contenu du colis

* [`jira-service-desk`](jira-service-desk/docker-compose.yml) un [Jira ServiceDesk] serveur autogéré en utilisant [streacs/atlassian-jira-servicedesk].
* [`openvpn-server`](openvpn-server/docker-compose.yml) un [OpenVPN] serveur en utilisant [kylemanna/openvpn].
* [`rutorrent-client`](rutorrent-client/docker-compose.yml) un client torrent avec une interface web en utilisant [bishof/torrent].
* [`unifi`](unifi/docker-compose.yml) un Ubiquiti Unifi contrôleur pour la gestion UAP en utilisant [jacobalberty/unifi].

[Docker Compose]: https://docs.docker.com/compose/
[Jira ServiceDesk]: https://www.atlassian.com/fr/software/jira/service-desk
[OpenVPN]: https://openvpn.net/
[bishof/torrent]: https://hub.docker.com/r/bishof/torrent
[jacobalberty/unifi]: https://hub.docker.com/r/jacobalberty/unifi
[kylemanna/openvpn]: https://hub.docker.com/r/kylemanna/openvpn
[streacs/atlassian-jira-servicedesk]: https://hub.docker.com/r/streacs/atlassian-jira-servicedesk
