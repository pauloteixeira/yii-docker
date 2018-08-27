
# Imagem Docker para Framework Yii2

Este é o repositório do ambiente de desenvolvimento com [Yii 2.0 Framework](http://www.yiiframework.com/).

> ## Status
> Este é um trabalho em andamento e deve ser usado com cautela.

## Descrição

As imagens Docker usadas para a construção do ambiente são imagens oficiais (Ngnix, PHP-FPM e Composer). Para atender as dependências relacionadas ao PHP são instaladas extensões, assim como pacotes debian para atendê-las.

> ## Versões disponíveis
>Nginx: Última versão usada pela imagem [Docker](https://hub.docker.com/_/nginx/) oficial.
>
>PHP-FPM: Versão 7.0-fpm usada pela imagem [Docker](https://hub.docker.com/_/php/) oficial.
>
>Composer: Última versão usada pela imagem [Docker](https://hub.docker.com/_/composer/) oficial.
>
>...

## Instalação

```bash
    cp .env-exemplo .env
```

Verifique o usuário que você usa em seu sistema e altere o valor de `USER_ID` em `.env` caso seja necessário.

```bash
    id -u
```

Por padrão, `HTTP_PROXY` está definido com o valor `http://proxy.rio.rj.gov.br:8080`, caso você não precise de um proxy para acessar servidores essenciais como github, deixe em branco.

> **Nota:** A maioria dos pacotes Composer estão em repositórios hospedados no Git Hub.

Crie um token de acesso pessoal no [Git Hub](https://github.com/settings/tokens/new?scopes=repo) e defina a variável `GITHUB_OAUTH` em .env

## Building

    docker-compose build

## Testando

    docker-compose run --rm php php /tests/requirements.php
> **Nota:** O script de testes foi extraído da imagem oficial do Yii2 em [https://github.com/yiisoft/yii2-docker/tree/master/tests](https://github.com/yiisoft/yii2-docker/tree/master/tests)
