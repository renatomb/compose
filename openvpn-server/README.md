# OpenVPN Server

## Visão geral
Configuração para o container `kylemanna/openvpn`, permitindo criar um servidor OpenVPN com geração de certificados e perfis de cliente.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Porta UDP 1194 liberada no firewall e roteada para o host.
- Variáveis de ambiente (ou flags) configuradas durante o setup inicial.

## Como usar
1. Gere a configuração inicial e certificados:
   ```bash
   docker compose run --rm openvpn ovpn_genconfig -u udp://SEU_DOMINIO_OU_IP
   docker compose run --rm openvpn ovpn_initpki
   ```
2. Suba o serviço com `docker compose up -d`.
3. Crie perfis de cliente:
   ```bash
   docker compose run --rm openvpn easyrsa build-client-full nome-do-cliente nopass
   docker compose run --rm openvpn ovpn_getclient nome-do-cliente > nome-do-cliente.ovpn
   ```
4. Distribua os perfis `.ovpn` para os usuários.

## Configuração
- **Imagem**: `kylemanna/openvpn`.
- **Porta**: `1194/udp` mapeada para o host.
- **Capacidades**: `NET_ADMIN` para manipular interfaces de rede.
- **Volume**: `./openvpn:/etc/openvpn` guarda configurações, certificados e logs.

## Manutenção
- Faça backup do diretório `./openvpn`.
- Para revogar um cliente: `docker compose run --rm openvpn ovpn_revokeclient <nome>`.
- Atualize a imagem com `docker compose pull && docker compose up -d`.

---
Autor: Renato Monteiro Batista
