# Kiwix Serve

## Visão geral
Roda o [Kiwix-serve](https://www.kiwix.org/) para disponibilizar conteúdo offline de arquivos `.zim` (Wikipedia, Wikilivros, etc.) via HTTP.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Arquivos `.zim` copiadas para o diretório do projeto.
- Porta livre (padrão 8666) no host.

## Como usar
1. Faça download dos arquivos `.zim` desejados e coloque-os na raiz do diretório `kiwix-serve`.
2. Inicie com `docker compose up -d`.
3. Acesse `http://localhost:8666` e navegue pelos conteúdos.

## Configuração
- **Imagem**: `ghcr.io/kiwix/kiwix-serve:3.7.0`.
- **Porta**: `8666:8080` (ajuste o lado esquerdo conforme necessário).
- **Volume**: `.:/data` expõe todos os `.zim` para o container.
- **Comando**: `*.zim` instruindo o Kiwix a servir todos os arquivos disponíveis; você pode apontar para um arquivo específico se preferir.

## Manutenção
- Atualize as coleções substituindo os `.zim` no diretório compartilhado.
- Atualize a imagem com `docker compose pull`.
- Monitore com `docker compose logs -f kiwix-serve` se precisar validar carregamento.

---
Autor: Renato Monteiro Batista
