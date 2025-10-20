# MeTube

## Visão geral
Executa o [MeTube](https://github.com/alexta69/metube), interface web para baixar vídeos e áudios de diversas plataformas utilizando o `yt-dlp`.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Espaço em disco no volume `./downloads` para armazenar mídias.
- (Opcional) Proxy ou cookies caso precise autenticação em plataformas específicas.

## Como usar
1. Ajuste o diretório `./downloads` ou crie um link simbólico para o local desejado.
2. Se preferir outra porta de acesso, altere o valor antes dos dois pontos na porta `8081:8081`.
3. Inicie com `docker compose up -d`.
4. Acesse `http://localhost:8081` e cole URLs para download.

## Configuração
- **Imagem**: `ghcr.io/alexta69/metube`.
- **Porta**: `8081` no host.
- **Volume**: `./downloads:/downloads` guarda os arquivos baixados.
- **Variáveis**: é possível adicionar parâmetros de timezone, proxies ou limite de tarefas via variáveis extras (consulte README oficial).

## Manutenção
- Limpe o diretório de downloads conforme necessidade.
- Atualize a imagem com `docker compose pull`.
- Monitore com `docker compose logs -f metube` para acompanhar downloads.

---
Autor: Renato Monteiro Batista
