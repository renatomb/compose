# n8n

## Visão geral
Executa o [n8n](https://n8n.io/), ferramenta de automação low-code com suporte a webhooks, agendamentos e integrações com centenas de serviços.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Domínio público configurado para receber webhooks, caso necessário.
- Volume `./.n8n` com espaço para fluxos e credenciais.

## Como usar
1. Ajuste a porta antes dos dois pontos em `56789:5678` para alguma livre no host.
2. Substitua `WEBHOOK_URL` pelo domínio/URL público que o n8n utilizará (incluindo protocolo).
3. Opcionalmente defina variáveis adicionais (ex.: `N8N_ENCRYPTION_KEY`, `TZ`, `EXECUTIONS_DATA_SAVE_ON_SUCCESS`).
4. Inicie com `docker compose up -d`.
5. Acesse `http://localhost:56789` para criar sua conta de administrador.

## Configuração
- **Imagem**: `n8nio/n8n`.
- **Portas**: mapeamento host -> container `56789:5678`.
- **Variáveis principais**:
  - `WEBHOOK_URL`: URL absoluta utilizada para webhooks.
  - `EXECUTIONS_PROCESS`: modo de processamento (`main` ou `queue`).
- **Volume**: `./.n8n:/home/node/.n8n` armazena fluxos, credenciais e arquivos temporários.

## Manutenção
- Faça backup do diretório `./.n8n`.
- Atualize com `docker compose pull`.
- Para executar atualizações/migrações seguras, pare o container (`docker compose down`) e suba novamente após o pull.

---
Autor: Renato Monteiro Batista
