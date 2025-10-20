# Nginx Proxy Manager

## Visão geral
Stack para o [Nginx Proxy Manager](https://nginxproxymanager.com/), interface web que facilita a gestão de proxys reversos, certificados TLS Let’s Encrypt e redirecionamentos.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Portas 80, 81 e 443 livres no host (ajuste se já estiverem sendo usadas).
- DNS apontando para o servidor caso deseje emitir certificados públicos.

## Como usar
1. Se precisar de portas diferentes, altere o lado esquerdo dos mapeamentos `80:80`, `81:81` e `443:443`.
2. Garanta que os diretórios `./data` e `./letsencrypt` existam e tenham permissões adequadas.
3. Inicie com `docker compose up -d`.
4. Acesse `http://localhost:81` para o painel administrativo (usuário padrão `admin@example.com` / senha `changeme`).

## Configuração
- **Imagem**: `jc21/nginx-proxy-manager:latest`.
- **Volumes**:
  - `./data:/data`: banco SQLite e configurações.
  - `./letsencrypt:/etc/letsencrypt`: certificados SSL gerenciados.
- **Variáveis**: você pode descomentar `environment` para customizar `DB_SQLITE_FILE` ou desabilitar IPv6.
- **Portas**:
  - `80`: HTTP público.
  - `443`: HTTPS público.
  - `81`: painel administrativo.

## Default Administrator User

- Email: admin@example.com
- Password: changeme

## Manutenção
- Faça backup dos diretórios `./data` e `./letsencrypt`.
- Atualize com `docker compose pull`.
- Monitore logs com `docker compose logs -f app`.

---
Autor: Renato Monteiro Batista
