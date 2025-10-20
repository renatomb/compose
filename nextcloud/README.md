# Nextcloud

## Visão geral
Implanta uma instância do [Nextcloud](https://nextcloud.com/), suíte de colaboração e sincronização de arquivos self-hosted.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Volumes persistentes configurados (mapeados em `./nextcloud/...`).
- Banco de dados externo recomendado (PostgreSQL ou MariaDB) para ambientes de produção — este stack inclui apenas a aplicação.

## Como usar
1. Ajuste o lado esquerdo da porta `8080:80` se necessitar de outra porta.
2. Certifique-se de que os diretórios `./nextcloud/*` existem e possuem permissões corretas.
3. Suba com `docker compose up -d`.
4. Acesse `http://localhost:8080` para concluir o assistente, apontando para o banco de dados desejado.

## Configuração
- **Volumes**:
  - `./nextcloud/nextcloud:/var/www/html`: código e apps padrão.
  - `./nextcloud/app:/var/www/html/custom_apps`: apps personalizados.
  - `./nextcloud/config:/var/www/html/config`: configurações.
  - `./nextcloud/data:/var/www/html/data`: arquivos de usuários.
  - `./nextcloud/theme:/var/www/html/themes/<SEU_TEMA>`: customização opcional.
- **Porta**: `8080` no host → `80` no container.
- **Imagem**: `nextcloud` (última versão estável).

## Manutenção
- Faça backup frequente de `./nextcloud/config` e `./nextcloud/data`.
- Atualize com `docker compose pull && docker compose up -d`.
- Considere integrar proxy reverso com TLS (ex.: Nginx Proxy Manager) para acesso seguro.

---
Autor: Renato Monteiro Batista
