# compose

[🇧🇷Instruções em Português🇧🇷](LEIAME.md) | [🇮🇹Instruzione Italiane🇮🇹](LEGGIMI.md)

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

If you need multiple containers in the same file, merge the containers you need in a single `docker-compose.yml`, when merging remember to keep only the first `version` line and make any necessary changes.

## Package contents

* `jiraservicedesk.yml` a [Jira ServiceDesk] self managed server using [streacs/atlassian-jira-servicedesk].
* `openvpn.yml` an [OpenVPN] server using [kylemanna/openvpn].
* `torrent.yml` a torrent client with web interface using [bishof/torrent].
* `unifi.yml` an Ubiquiti Unifi controller for UAP management using [jacobalberty/unifi].

[Docker Compose]: https://docs.docker.com/compose/
[Jira ServiceDesk]: https://www.atlassian.com/software/jira/service-desk
[OpenVPN]: https://openvpn.net/
[bishof/torrent]: https://hub.docker.com/r/bishof/torrent
[jacobalberty/unifi]: https://hub.docker.com/r/jacobalberty/unifi
[kylemanna/openvpn]: https://hub.docker.com/r/kylemanna/openvpn
[streacs/atlassian-jira-servicedesk]: https://hub.docker.com/r/streacs/atlassian-jira-servicedesk
