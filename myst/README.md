# Myst Node

## Visão geral
Executa um nó do [Myst Network](https://mystnodes.com/), plataforma de VPN descentralizada que permite monetizar largura de banda oferecendo serviços de proxy.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Porta 4449 liberada (TCP) para comunicação com a rede Myst.
- Aceitar os termos de uso da Myst Network.

## Como usar
1. Confirme que o comando `service --agreed-terms-and-conditions` está aderente à sua aceitação dos termos.
2. Ajuste o volume `./myst-data` para o caminho onde deseja persistir as chaves.
3. Inicie com `docker compose up -d`.
4. Utilize a CLI `myst` ou painel da Myst Network para registrar o nó e gerenciar ganhos.

## Configuração
- **Imagem**: `mysteriumnetwork/myst:latest`.
- **Portas**: `4449:4449`.
- **Volume**: `./myst-data:/var/lib/mysterium-node` guarda chaves e configurações.
- **Capacidades**: `NET_ADMIN` é necessário para criação de interfaces virtuais.
- **Comando**: executa o serviço principal com aceite dos termos padrão.

## Manutenção
- Atualize a imagem com `docker compose pull`.
- Backup do diretório `./myst-data` para preservar identidade do nó.
- Monitore com `docker compose logs -f myst`.

---
Autor: Renato Monteiro Batista
