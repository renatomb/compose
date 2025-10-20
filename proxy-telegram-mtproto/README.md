# Proxy MTProto (Telegram)

## Visão geral
Provisiona o proxy MTProto oficial do Telegram para oferecer acesso seguro ao Telegram em redes restritas.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Porta 443 disponível no host.
- Gerar secret/token via script oficial do Telegram (`generate-secrets.sh`) ou manualmente.

## Como usar
1. Crie o diretório `./proxy-config` e adicione os arquivos `config.json`, `secret` ou outros exigidos pela documentação oficial.
2. Ajuste as permissões do diretório para que o container possa ler os arquivos.
3. Inicie com `docker compose up -d`.
4. Verifique os logs com `docker compose logs -f mtproto-proxy` para confirmar o registro.
5. Distribua o link `tg://proxy?server=<host>&port=443&secret=<secret>` aos usuários.

## Configuração
- **Imagem**: `telegrammessenger/proxy:latest`.
- **Porta**: `443` mapeada diretamente.
- **Volume**: `./proxy-config:/data` armazena configurações e chaves.
- **Variáveis**: adicione extras (por exemplo, `SECRET`, `TAG`) na seção `environment` se preferir parametrização pela compose.

## Manutenção
- Atualize os arquivos de configuração conforme o Telegram publicar mudanças.
- Faça backup de `./proxy-config`.
- Atualize a imagem com `docker compose pull`.

---
Autor: Renato Monteiro Batista
