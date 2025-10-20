# Cloudflare Tunnel

## Visão geral
Este stack prepara um túnel Cloudflare (`cloudflared`) para expor serviços internos com segurança usando a infraestrutura da Cloudflare.

## Pré-requisitos
- Docker 20.10+ com o plugin Docker Compose v2.
- Uma conta Cloudflare com túnel criado e token de acesso.

## Como usar
1. Substitua `<INSERIR TOKEN AQUI>` no `docker-compose.yml` pelo token gerado no painel da Cloudflare.
2. (Opcional) Ajuste os mapeamentos de portas caso queira usar outra porta host.
3. Inicie com `docker compose up -d`.
4. Visualize os logs em `docker compose logs -f cloudflared` para garantir que o túnel autenticou corretamente.

## Configuração
- **Imagem**: `cloudflare/cloudflared:latest`.
- **Portas**: nenhuma porta local é exposta por padrão; o túnel encaminha tráfego pela infraestrutura da Cloudflare.
- **Comando**: `tunnel --no-autoupdate run --token ...` garante que a versão da imagem é controlada manualmente.

## Manutenção
- Atualize periodicamente a imagem com `docker compose pull`.
- Use `docker compose restart cloudflared` após alterar o token ou parâmetros.

---
Autor: Renato Monteiro Batista
