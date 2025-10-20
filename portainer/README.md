# Portainer CE

## Visão geral
Executa o [Portainer Community Edition](https://www.portainer.io/), painel de gestão para Docker, Swarm e Kubernetes com interface web intuitiva.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Acesso ao socket Docker (`/var/run/docker.sock`) ou Endpoint remoto configurado.
- Porta 9000 disponível no host (pode ser alterada).

## Como usar
1. Verifique se o socket Docker pode ser montado em modo somente leitura (`:ro`). Caso utilize Docker remoto, remova o bind e configure um endpoint TCP seguro.
2. Inicie com `docker compose up -d`.
3. Acesse `http://localhost:9000` e crie o usuário administrador.
4. Registre o endpoint desejado (Docker local é detectado automaticamente via socket).

## Configuração
- **Imagem**: `portainer/portainer-ce:latest`.
- **Volumes**:
  - `/var/run/docker.sock:/var/run/docker.sock:ro`: acesso ao Docker local.
  - `./portainer-data:/data`: configuração e banco interno.
  - `/etc/localtime:/etc/localtime:ro`: mantém fuso horário correto.
- **Segurança**: `no-new-privileges:true` reduz privilégios dentro do container.

## Manutenção
- Backup regular do diretório `./portainer-data`.
- Atualização com `docker compose pull` seguida de `docker compose up -d`.
- Monitore logs com `docker compose logs -f portainer`.

---
Autor: Renato Monteiro Batista
