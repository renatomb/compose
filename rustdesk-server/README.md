# RustDesk Server

## Visão geral
Stack para hospedar os serviços `hbbs` e `hbbr` do [RustDesk](https://rustdesk.com/), permitindo controle remoto self-hosted com NAT traversal.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- DNS apontando para o host (necessário para o parâmetro `-r example.com:21117`).
- Portas TCP/UDP 21115-21119 liberadas no firewall.

## Como usar
1. Substitua `example.com` no comando do serviço `hbbs` pelo domínio ou IP público do servidor.
2. Gere e configure a chave de encriptação (`-k`) adequadamente; substitua `_` por um valor seguro.
3. Ajuste os volumes `./hbbs` e `./hbbr` para locais persistentes.
4. Inicie com `docker compose up -d`.
5. Configure os clientes RustDesk apontando para o host/domínio configurado.

## Configuração
- **Serviços**:
  - `hbbs`: serviço de rendezvous e broker.
  - `hbbr`: servidor de relay.
- **Portas expostas**:
  - `21115`, `21116`, `21116/udp`, `21118` (hbbs).
  - `21117`, `21119` (hbbr).
- **Volumes**:
  - `./hbbs:/root` e `./hbbr:/root`: armazenam chaves, configurações e logs.
- **Rede**: rede interna `rustdesk-net` isola a comunicação entre os contêineres.

## Manutenção
- Faça backup das pastas `./hbbs` e `./hbbr` (contêm chaves e certificados).
- Atualize com `docker compose pull`.
- Monitore com `docker compose logs -f hbbs` e `hbbr`.

---
Autor: Renato Monteiro Batista
