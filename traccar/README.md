# Traccar

Este projeto contém as informações necessárias para execução do TracCar usando docker, através do docker-compose.

## Visão geral
Configuração para o [Traccar](https://www.traccar.org/), plataforma de rastreamento GPS compatível com centenas de dispositivos e aplicativos móveis.

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Porta 8082 disponível para a interface web.
- Faixa de portas 5000-5150 aberta (TCP e UDP) para receber pacotes de rastreadores.

## Como usar
1. Ajuste as portas expostas se necessário (lembre-se de abrir a faixa correspondente no firewall).
2. Edite o arquivo `traccar.xml` conforme as necessidades de protocolo, notificações, banco de dados, etc. Ele é montado via volume `./traccar.xml`.
3. Inicie com `docker compose up -d`.
4. Acesse `http://localhost:8082` (usuário padrão `admin`, senha `admin`).

## Configuração
- **Imagem**: `traccar/traccar:latest`.
- **Portas**:
  - `8082`: UI administrativa.
  - `5000-5150`: portas padrão para dispositivos (TCP e UDP).
- **Volumes**:
  - `./logs:/opt/traccar/logs`: diretório de logs.
  - `./traccar.xml:/opt/traccar/conf/traccar.xml:ro`: arquivo de configuração principal (modo leitura).

## Manutenção
- Monitore `./logs` para acompanhar dispositivos e falhas.
- Atualize com `docker compose pull`.
- Faça backup do arquivo `traccar.xml` e de qualquer banco externo configurado.

## Conectando-se ao traccar usando o rastreador tk103

Os comandos a seguir devem ser enviados via SMS ao chip inserido no rastreador para configuração do mesmo. Todos os comandos estão considerando a senha padrão *123456* para configuração, ajuste os comandos conforme a sua senha configurada.

| comando  | descricao |
|---|---|
| `begin123456` | Iniciallização do rastreador   |
| `admin123456 849XXXXXXXX` | Configurando o telefone *849XXXXXXXX* como admin autorizado a enviar comandos para o rastreador, no exemplo o código de área é 84. |
| `imei123456` | O rastreador retornará o IMEI do dispositivo que deverá ser cadastrado no Traccar através da interface web. |
| `time zone123456 -3` | Configura o relógio para hora do Brasil. |
| `apn123456 zap.vivo.com.br` | Configura a APN do TK103 para operadora vivo. |
| `up123456 vivo vivo` | Configura usuario e senha para acesso a APN da vivo.  |
| `dns123456 host.example.com 5001` | Configura o servidor de trackar através de nome de host dns, exemplo o host seria *host.example.com* utilizando a porta *5001*. Para configurar via ip, o comando seria `adminip123456 127.203.203.203 5001` sendo necessário substituir o ip *127.203.203.203* para o IP público do servidor Traccar. |
| `gprs123456` | Habilita a comunicação do rastreador através da rede de dados móveis. |
| `fix030s030m***n123456` | Configura o rastreador para enviar informações a cada *30 segundos* quando o veículo estiver ligado em movimento e a cada *30 minutos* quando o veículo estiver desligado sem movimento. |
| `check123456` | Retorna, via sms, a configuração atual do rastreador. |

### Identificando a porta

No meu TK103 identifiquei que a porta de comunicação é a *5001*, ao tentar via porta web (configurada como 8082 no `docker-compose.yml`) simplesmente nada acontece. Se utilizar um rastreador diferente desse modelo recomendo a leitura do artigo [Traccar - Protocol Identification](https://www.traccar.org/identify-protocol/) do site do Traccar que tem informações adicionais como identificar o protocolo e porta corretos.

### Observações sobre o IMEI

Dispositivos que utilizam o protocolo TK103 (porta 5002) senviam um identificador de 12 dígitos no lugar do IMEI. Normalmente consiste dos últimos 11 dígitos do IMEI acrescidos de um 0 na frente. Por exemplo para o IMEI 123456789012345, o identificador seria 056789012345. A solução mais fácil para descobrir isso seria cadastrar dois dispositivos no traccar, um com o IMEI completo e o outro com o identificador e ver qual se comunica. Mais informações disponíveis na página [Traccar - Chinese clones](https://www.traccar.org/clones/).

## Banco de dados mysql

Utilize como referência o arquivo `traccar-mysql.xml`, faça as alterações necessárias e renomeie-o para `traccar.xml` antes de executar o `docker-compose`. Para informações adicionais visite [Traccar - Mysql Database](https://www.traccar.org/mysql/).

### Conectando em um servidor mysql existente que não esteja especificado no mesmo docker-compose

No exemplo a seguir considerei que já há um mysql executando em outro docker-compose, com nome da rede `rede_mysql`, deve-se incluir as seguintes linhas ao final do arquivo `docker-compose.yml`, após a seção *volumes*.

```
    networks:
      - rede_mysql

networks:
  rede_mysql:
    external: true
```
---
Autor: Renato Monteiro Batista
