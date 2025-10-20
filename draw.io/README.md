# draw.io (diagrams.net)

## Visão geral
Executa a versão self-hosted do draw.io/diagrams.net para criação colaborativa de diagramas diretamente no navegador.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Porta disponível para o serviço (padrão 8080) e, opcionalmente, 8443 se usar HTTPS interno.

## Como usar
1. Ajuste o mapeamento de portas no `docker-compose.yml` se precisar de outras portas no host.
2. Se utilizar HTTPS interno, configure certificados no container ou faça o offload em um proxy reverso externo.
3. Inicie com `docker compose up -d`.
4. Acesse `http://localhost:8080` para a interface web.

## Configuração
- **Imagem**: `jgraph/drawio`.
- **Portas**:
  - `8080:8080` (HTTP).
  - `8443:8443` (HTTPS interno).
- **Healthcheck**: verifica disponibilidade em `http://127.0.0.1:8080`; ajuste a URL conforme o cenário.
- **Persistência**: a aplicação é stateless; salve diagramas em plataformas externas (Git, Nextcloud, etc.).

## Manutenção
- Atualize com `docker compose pull && docker compose up -d`.
- Monitore com `docker compose logs -f drawio`.
- Para TLS gerenciado externamente, use um proxy como Nginx Proxy Manager ou Traefik.

---
Autor: Renato Monteiro Batista
