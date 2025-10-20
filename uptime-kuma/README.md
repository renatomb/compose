# Uptime Kuma

## Visão geral
Executa o [Uptime Kuma](https://github.com/louislam/uptime-kuma), monitor de disponibilidade com dashboards modernos e notificações integradas.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Porta 3001 disponível (pode ser alterada).
- Diretório `./uptime-kuma/data` com permissão de escrita.

## Como usar
1. Ajuste a porta antes dos dois pontos em `3001:3001` caso precise.
2. Garanta que o diretório de dados exista (`mkdir -p uptime-kuma/data`).
3. Suba com `docker compose up -d`.
4. Acesse `http://localhost:3001`, crie o usuário administrador e cadastre monitoramentos.

## Configuração
- **Imagem**: `louislam/uptime-kuma`.
- **Volume**: `./uptime-kuma/data:/app/data` mantém configurações, histórico e anexos.
- **Container name**: `uptime-kuma` simplifica comandos `docker compose logs -f uptime-kuma`.
- **Variáveis adicionais**: é possível definir `TZ`, SMTP, notificação por push, etc., adicionando-as em `environment`.

## Manutenção
- Realize backups do diretório `./uptime-kuma/data`.
- Atualize com `docker compose pull`.
- Utilize `docker compose logs -f uptime-kuma` para investigar falhas de monitoramento.

---
Autor: Renato Monteiro Batista
