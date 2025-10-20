# Apache Guacamole

## Visão geral
Provisiona o [Apache Guacamole](https://guacamole.apache.org/), gateway remoto sem cliente que oferece acesso RDP, VNC e SSH pelo navegador.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Volume `./postgres` com espaço suficiente para banco de dados e configurações (a imagem escolhida usa PostgreSQL embutido).
- Configure DNS/Proxy reverso caso deseje expor pela internet.

## Como usar
1. Opcionalmente edite o `docker-compose.yml` para alterar a porta `8080` ou o caminho do volume.
2. Suba o serviço com `docker compose up -d`.
3. Acesse `http://localhost:8080/guacamole`.
4. Se necessário, configure credenciais padrão no primeiro acesso.

## Configuração
- **Imagem**: `jwetzell/guacamole` (inclui servidor + banco).
- **Porta**: `8080` expõe a UI web.
- **Volumes**: `./postgres:/config` contém banco e arquivos persistentes.
- **Variáveis**: não há variáveis obrigatórias, mas você pode adicionar conforme documentação oficial (usuários, SMTP etc.).

## Manutenção
- Backup periódico do diretório `./postgres`.
- Atualize com `docker compose pull`.
- Monitore logs com `docker compose logs -f guacamole`.

---
Autor: Renato Monteiro Batista
