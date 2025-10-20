# Homepage

## Visão geral
Stack para o [Homepage](https://gethomepage.dev), painel personalizável que centraliza links, status e integrações com Docker/Kubernetes.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Permissão de leitura do socket Docker caso queira exibir containers.
- Configurações do `./config` preparadas conforme a documentação do Homepage.

## Como usar
1. Ajuste o diretório `./config` com os arquivos YAML de widgets, serviços e seções.
2. (Opcional) Mantenha o bind do socket Docker (`/var/run/docker.sock`) apenas se desejar mostrar containers e se aceitar o risco de segurança.
3. Inicie com `docker compose up -d`.
4. Acesse `http://localhost:7900`.

## Configuração
- **Porta**: `7900` no host apontando para `3000` no container.
- **Volumes**:
  - `./config:/app/config`: armazena configurações e ícones personalizados.
  - `/var/run/docker.sock:/var/run/docker.sock:ro`: integrações com Docker (opcional).
- **Imagem**: `ghcr.io/gethomepage/homepage:latest`.
- **Usuário**: caso opte por rodar com UID/GID específicos, ajuste o parâmetro `user` e remova o socket direto.

## Manutenção
- Organize backups do diretório de configuração.
- Atualize com `docker compose pull` e reinicie.
- Use `docker compose logs -f homepage` para resolver problemas de carregamento.

---
Autor: Renato Monteiro Batista
