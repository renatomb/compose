# Kimai

## Visão geral
Configuração mínima para rodar o [Kimai](https://www.kimai.org/), sistema de time tracking e faturamento baseado em PHP.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Banco MySQL/MariaDB acessível (externo ou container separado).
- Variável `DATABASE_URL` ajustada com credenciais válidas.

## Como usar
1. Edite `docker-compose.yml` substituindo `username`, `password` e `mysql-server.local` na variável `DATABASE_URL` pelo host e credenciais reais.
2. Opcionalmente configure mapeamentos de volumes para persistir plugins, dados e logs (consulte a documentação oficial).
3. Inicie com `docker compose up -d`.
4. Acesse `http://localhost:8001`.

## Configuração
- **Imagem**: `kimai/kimai2:apache` (Apache + PHP).
- **Porta**: `8001` no host conectando no Apache interno.
- **Ambiente**:
  - `DATABASE_URL`: string no formato `mysql://usuario:senha@host:porta/banco`.
- **TTY/Stdin**: habilitados para facilitar execuções interativas (como `kimai:reload` via `docker compose exec`).

## Manutenção
- Atualize a imagem com `docker compose pull`.
- Execute `docker compose exec kimai bin/console kimai:reload` para aplicar migrações quando atualizar.
- Realize backups do banco de dados externo regularmente.

---
Autor: Renato Monteiro Batista
