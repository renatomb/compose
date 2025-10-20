# UniFi Network Controller

## Visão geral
Provisiona o controlador UniFi (imagem `jacobalberty/unifi`) para gerenciar access points, switches e roteadores da Ubiquiti.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Portas TCP/UDP necessárias liberadas no firewall e roteadas para o host.
- Volume `./unifi` com espaço para banco MongoDB embutido e configurações.

## Como usar
1. Ajuste as portas mapeadas caso alguma conflite com serviços locais (leia a documentação da Ubiquiti para portas requeridas).
2. Defina o timezone correto em `TZ` (ex.: `America/Sao_Paulo`).
3. Suba com `docker compose up -d`.
4. Acesse `https://localhost:8443` para finalizar o assistente.

## Configuração
- **Imagem**: `jacobalberty/unifi:stable`.
- **Portas expostas**:
  - `8080/tcp`: portal inform/adopt.
  - `8443/tcp`: interface web.
  - `3478/udp`: STUN.
  - `10001/udp`: descoberta de dispositivos.
- **Volume**: `./unifi:/unifi` guarda banco de dados e backups.
- **Variáveis**: `TZ` define o fuso horário; adicione outras conforme necessidades (ex.: `UNIFI_HTTP_PORT`).

## Manutenção
- Faça backup regular do diretório `./unifi`.
- Antes de atualizar, execute `docker compose pull` seguido de `docker compose up -d`.
- Monitore com `docker compose logs -f unifi`.

---
Autor: Renato Monteiro Batista
