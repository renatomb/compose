# MariaDB + phpMyAdmin

## Visão geral
Provisiona um banco MariaDB e a interface phpMyAdmin para administração web.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Defina uma senha forte em `MYSQL_ROOT_PASSWORD` antes de iniciar.
- Porta 8080 disponível no host (pode ser adaptada).

## Como usar
1. Edite o `docker-compose.yml` e troque `substituirPorUmaSenhaSegura` por uma senha forte.
2. (Opcional) Adicione variáveis adicionais para criar bases/usuários via `MYSQL_DATABASE`, `MYSQL_USER`, etc.
3. Suba com `docker compose up -d`.
4. Acesse `http://localhost:8080` e conecte-se com usuário `root` e a senha definida.

## Configuração
- **Serviços**:
  - `db`: usa `mariadb:10.6`.
  - `phpmyadmin`: imagem oficial do phpMyAdmin (última versão).
- **Volumes**: `./dados:/var/lib/mysql` persiste os dados do banco.
- **Variáveis**: `PMA_ARBITRARY=1` permite conectar-se a outros hosts MySQL manualmente.

## Manutenção
- Faça backup do diretório `./dados`.
- Atualize as imagens com `docker compose pull`.
- Monitore com `docker compose logs -f db` e `phpmyadmin`.

---
Autor: Renato Monteiro Batista
