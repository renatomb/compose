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

Se você necessitar multiplos contêiners no mesmo arquivo, mescle o conteúdo dos arquivos no mesmo arquivo `docker-compose.yml`, ao mesclar lembre-se de manter apenas a primeira linha contendo `version` e faça todas as mudanças que necessitar.

## Conteúdo do pacote

* `jiraservicedesk.yml` um servidor interno do [Jira ServiceDesk] usando [streacs/atlassian-jira-servicedesk].
* `openvpn.yml` um servidor [OpenVPN] usando [kylemanna/openvpn].
* `torrent.yml` um cliente torrent com interface web usando [bishof/torrent].
* `unifi.yml` um controlador Ubiquiti Unifi para gerenciamento de equipamentos UAP usando [jacobalberty/unifi].

[Docker Compose]: https://docs.docker.com/compose/
[Jira ServiceDesk]: https://www.atlassian.com/br/software/jira/service-desk
[OpenVPN]: https://openvpn.net/
[bishof/torrent]: https://hub.docker.com/r/bishof/torrent
[jacobalberty/unifi]: https://hub.docker.com/r/jacobalberty/unifi
[kylemanna/openvpn]: https://hub.docker.com/r/kylemanna/openvpn
[streacs/atlassian-jira-servicedesk]: https://hub.docker.com/r/streacs/atlassian-jira-servicedesk
