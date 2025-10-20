# Seafile

## Visão geral
Hospeda o [Seafile](https://www.seafile.com/), plataforma de sincronização e colaboração em arquivos, incluindo dependências MariaDB e Memcached.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Diretórios persistentes configurados para banco e dados (`/path/to/...` e `/seafile` devem ser ajustados).
- Porta disponível (padrão 8999) e DNS opcional para acesso externo.

## Como usar
1. Substitua `/path/to/your/seafile/folder/or/data/store` pelo caminho real onde o MariaDB deve ser persistido.
2. Ajuste a senha em `MYSQL_ROOT_PASSWORD` e `DB_ROOT_PASSWD` para algo seguro.
3. (Opcional) Altere o fuso horário em `TIME_ZONE`.
4. Inicie com `docker compose up -d`.
5. Acesse `http://localhost:8999` após a inicialização para concluir a configuração pelo wizard.

## Configuração
- **Serviços**:
  - `db`: MariaDB 10.5 (persistência obrigatória).
  - `memcached`: otimiza desempenho e cache.
  - `seafile`: aplicação principal.
- **Portas**: `8999:80` expõe o front-end.
- **Volumes**:
  - MariaDB: `...:/var/lib/mysql`.
  - Seafile: `/seafile:/shared` (ajuste para seu diretório real).
- **Variáveis**: defina `DB_HOST`, `DB_ROOT_PASSWD` coerente com a senha definida em `db`.

## Default Administrator User

- Email: me@example.com
- Password: asecret

## Manutenção
- Realize backup de `/shared` e do diretório do banco.
- Atualize imagens com `docker compose pull`.
- Consulte logs com `docker compose logs -f seafile`.

---
Autor: Renato Monteiro Batista
