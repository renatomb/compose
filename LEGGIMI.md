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

Se hai bisogno di più contenitori nello stesso file, unisci i contenitori di cui hai bisogno in un'unico `docker-compose.yml`, durante l'unione ricordati di mantenere solo la prima riga `version` e di apportare le modifiche necessarie.

## Contenuto della confezione

* `jiraservicedesk.yml` uno [Jira ServiceDesk] server autogestito utilizzando [streacs/atlassian-jira-servicedesk].
* `openvpn.yml` uno [OpenVPN] server utilizzando [kylemanna/openvpn].
* `torrent.yml` uno client torrent con un'interfaccia web utilizzando [bishof/torrent].
* `unifi.yml` uno Ubiquiti Unifi controller per gestione UAP utilizzando [jacobalberty/unifi].

[Docker Compose]: https://docs.docker.com/compose/
[Jira ServiceDesk]: https://www.atlassian.com/it/software/jira/service-desk
[OpenVPN]: https://openvpn.net/
[bishof/torrent]: https://hub.docker.com/r/bishof/torrent
[jacobalberty/unifi]: https://hub.docker.com/r/jacobalberty/unifi
[kylemanna/openvpn]: https://hub.docker.com/r/kylemanna/openvpn
[streacs/atlassian-jira-servicedesk]: https://hub.docker.com/r/streacs/atlassian-jira-servicedesk
