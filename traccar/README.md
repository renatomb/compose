# Executando o TracCar em Docker

Este projeto contém as informações necessárias para execução do TracCar usando docker, através do docker-compose.

## Instruções de uso

Caso necessário altere o arquivo `traccar.xml` para configurar o banco de dados desejado.

### Execute o docker através do docker-compose

```bash
docker-compose up -d
```

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
