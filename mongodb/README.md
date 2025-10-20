# MongoDB + Mongo Express

## Visão geral
Stack simples com MongoDB e a interface Mongo Express para administração via navegador.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Ajuste das credenciais padrão (`root`/`example`) para algo seguro antes de subir em produção.
- Porta 8081 disponível para o Mongo Express.

## Como usar
1. Altere `MONGO_INITDB_ROOT_USERNAME`/`MONGO_INITDB_ROOT_PASSWORD` e as variáveis correspondentes do Mongo Express.
2. Inicie com `docker compose up -d`.
3. Conecte-se ao MongoDB em `mongodb://root:<senha>@localhost:27017`.
4. Acesse `http://localhost:8081` para a UI do Mongo Express.

## Configuração
- **Serviços**:
  - `mongo`: banco de dados oficial.
  - `mongo-express`: interface web administrativa.
- **Volumes**: `./dados:/data/db` persiste os dados do Mongo.
- **Variáveis**:
  - `MONGO_INITDB_ROOT_USERNAME`/`PASSWORD`: usuário root inicial.
  - `ME_CONFIG_*`: credenciais e URL de conexão para o Mongo Express.

## Manutenção
- Realize backups do diretório `./dados`.
- Atualize com `docker compose pull`.
- Use `docker compose logs -f mongo` e `mongo-express` para diagnosticar problemas.

---
Autor: Renato Monteiro Batista
