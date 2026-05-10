# ruTorrent Client

## Visão geral
Executa a imagem `renatomb/rutorrent`, combinando rTorrent + ruTorrent para gerenciamento de downloads BitTorrent via navegador.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Diretórios `./downloads`, `./config` e `./logs` com permissão de escrita.
- Portas disponíveis: 51413 (TCP/UDP) para tráfego BitTorrent, 51414 para DHT e 8666/HTTP para a interface.

## Como usar
1. Ajuste, se necessário, as portas antes dos dois pontos (por exemplo, `51413`, `8666` e `51414`).
2. Suba com `docker compose up -d`.
3. Acesse `http://localhost:8089` para abrir o ruTorrent.
4. Configure preferências de download dentro da interface (diretórios, limites de velocidade, RSS etc.).

## Configuração
- **Imagem**: `renatomb/rutorrent`.
- **Portas**:
  - `51413`: porta TCP/UDP principal para conexões BitTorrent.
  - `8666`: interface web ruTorrent.
  - `51414`: DHT
- **Volumes**:
  - `./downloads`: guarda torrents e arquivos baixados.
  - `./config`: configurações do rTorrent/ruTorrent.
  - `./logs`: logs.

## Manutenção
- Faça backup dos diretórios de dados e configurações.
- Atualize com `docker compose pull`.
- Verifique os logs com `docker compose logs -f rutorrent`.

---
Autor: Renato Monteiro Batista
