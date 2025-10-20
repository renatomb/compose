# MeshCentral

## Visão geral
Provisiona o [MeshCentral](https://meshcentral.com/), plataforma de gerenciamento remoto para endpoints com suporte a acesso remoto, inventário e chat.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- DNS apontando para o host (necessário para certificados e convites).
- Ajustes de firewall liberando a porta HTTP/HTTPS desejada (padrão 8090 -> 443).

## Como usar
1. Edite as variáveis de ambiente no `docker-compose.yml`:
   - `HOSTNAME`: domínio público que apontará para o serviço.
   - `REVERSE_PROXY` e `REVERSE_PROXY_TLS_PORT` se usar proxy reverso.
   - Demais flags (`IFRAME`, `ALLOW_NEW_ACCOUNTS`, `WEBRTC`) conforme sua política.
2. Suba com `docker compose up -d`.
3. Acesse `https://seu-dominio:8090` (ou porta configurada) para concluir o assistente.

## Configuração
- **Portas**: `8090:443` expõe o serviço TLS interno na porta 8090 do host.
- **Volumes**:
  - `./data:/opt/meshcentral/meshcentral-data`: configurações, certificados, banco.
  - `./user_files:/opt/meshcentral/meshcentral-files`: uploads de usuários.
- **Imagem**: `typhonragewind/meshcentral` com atualizações automáticas embutidas.

## Manutenção
- Faça backup frequente de `./data` e `./user_files`.
- Atualize com `docker compose pull && docker compose up -d`.
- Consulte logs com `docker compose logs -f meshcentral`.

---
Autor: Renato Monteiro Batista
