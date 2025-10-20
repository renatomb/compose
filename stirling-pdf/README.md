# Stirling PDF

## Visão geral
Stack para rodar o [Stirling PDF](https://github.com/Stirling-Tools/Stirling-PDF), suíte web para manipulação de arquivos PDF (dividir, mesclar, OCR, conversão, etc.).

## Pré-requisitos
- Docker 20.10+ com plugin Docker Compose v2.
- Diretórios `./trainingData` e `./configs` criados com permissões adequadas.
- Portas disponíveis para a interface web (padrão 8080).

## Como usar
1. Ajuste os volumes:
   - `./trainingData` deve conter os pacotes OCR adicionais (coloque arquivos `.traineddata` do Tesseract).
   - `./configs` guarda configurações persistentes.
   - (Opcional) Descomente `customFiles` para temas, fontes, etc.
2. Altere a porta antes dos dois pontos se necessário.
3. Defina variáveis adicionais conforme recursos desejados (`DOCKER_ENABLE_SECURITY`, `LANGS`, etc.).
4. Inicie com `docker compose up -d`.
5. Acesse `http://localhost:8080`.

## Configuração
- **Imagem**: `frooodle/s-pdf:latest`.
- **Porta**: `8080:8080`.
- **Variáveis**:
  - `DOCKER_ENABLE_SECURITY`: habilita recursos de segurança extra (false por padrão).
  - `INSTALL_BOOK_AND_ADVANCED_HTML_OPS`: instala dependências opcionais.
  - `LANGS`: idiomas adicionais do OCR (ex.: `pt_BR`).

## Manutenção
- Atualize com `docker compose pull`.
- Monitore logs com `docker compose logs -f stirling-pdf`.
- Faça backup dos diretórios `./configs` e `./trainingData`.

---
Autor: Renato Monteiro Batista
