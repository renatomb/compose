# ruTorrent Client

## Visão geral
Executa a imagem `bishof/torrent`, combinando rTorrent + ruTorrent para gerenciamento de downloads BitTorrent via navegador.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Diretórios `./torrent/data` e `./torrent/cfg` com permissão de escrita.
- Portas disponíveis: 49184/TCP para tráfego BitTorrent e 8089/HTTP para a interface.

## Como usar
1. Ajuste, se necessário, as portas antes dos dois pontos (por exemplo, `49184` e `8089`).
2. Suba com `docker compose up -d`.
3. Acesse `http://localhost:8089` para abrir o ruTorrent.
4. Configure preferências de download dentro da interface (diretórios, limites de velocidade, RSS etc.).

## Configuração
- **Imagem**: `bishof/torrent`.
- **Portas**:
  - `49184`: porta TCP principal para conexões BitTorrent.
  - `8089`: interface web ruTorrent.
- **Volumes**:
  - `./torrent/data:/data`: guarda torrents e arquivos baixados.
  - `./torrent/cfg:/home/torrent`: configurações do rTorrent/ruTorrent.

## Manutenção
- Faça backup dos diretórios de dados e configurações.
- Atualize com `docker compose pull`.
- Verifique os logs com `docker compose logs -f torrent`.

---
Autor: Renato Monteiro Batista
