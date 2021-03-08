# PROPOSTA DE UMA ARQUITETURA BASEADA EM MICROSSERVIÇOS PARA UM SISTEMA DE GERENCIAMENTO DE CURSOS OPEN SOURCE

Este repositório contém a configuração ambiente do Moodle para utilização em contêineres.

## Pré-requisitos

- [Docker](https://docs.docker.com)
- [Docker-Compose](https://docs.docker.com/compose/)

## Como Utilizar

Para criar o ambiente do Moodle, basta efetuar o download deste reposítorio, estando no mesmo diretório do arquivo do **docker-compose.yaml**, podemos rodar o comando abaixo que vai executar o Docker-Compose e criar e iniciar todo o ambiente:

```bash
docker-compose up -d
```

Para remover todo o ambiente, estando no mesmo diretório do arquivo do **docker-compose.yaml**, basta executar o comando abaixo:

```bash
docker-compose down -d
```

## Imagens Utilizadas

Para criação do ambiente em forma de contêiner iremos utilizar imagens Docker já disponíveis, sendo elas:

- [bitnami/moodle](https://hub.docker.com/r/bitnami/moodle)
- [bitnami/mariadb](https://hub.docker.com/r/bitnami/mariadb)
- [bitnami/redis](https://hub.docker.com/r/bitnami/redis)
- [moodlehq/moodle-mlbackend-python](https://hub.docker.com/r/moodlehq/moodle-mlbackend-python)

## Variáveis de ambiente

As variáveis de ambiente servem para você poder ajustar a configuração da instância passando uma ou mais variáveis de ambiente no arquivo do docker-compose.

#### Contêiner do Moodle

Variáveis de ambiente suportadas pela imagem do contêiner do Moodle são:

###### Configurações de Usuário e do Site

- `MOODLE_USERNAME`: Nome do usuário do Moodle. Valor padrão: **usuario**
- `MOODLE_PASSWORD`: Senha do usuário do Moodle. Valor padrão: **bitnami**
- `MOODLE_SITE_NAME`: Nome do site do Moodle. Valor padrão: **New Site**

###### Configurações de Banco de Dados

- `MOODLE_DATABASE_TYPE`: Tipo do banco de dados. Valor padrão: **mariadb**
- `MOODLE_DATABASE_HOST`: Hostname para o banco de dados. Valor padrão: **mariadb**
- `MOODLE_DATABASE_PORT_NUMBER`: Porta utilizada pelo banco de dados. Valor padrão: **3306**
- `MOODLE_DATABASE_NAME`: Nome do banco de dados que o Moodle utilizará para conexão. Valor padrão: **moodledb**
- `MOODLE_DATABASE_USER`: Nome do usuário que o Moodle utilizará para conexão ao banco de dados. Valor padrão: **moodledbuser**
- `MOODLE_DATABASE_PASSWORD`: Senha do usuário que o Moodle utilizará para conexão ao banco de dados. Valor padrão: **moodledbpassword**.

#### Contêiner do Banco de Dados (MariaDB)

Variáveis de ambiente suportadas pela imagem do contêiner do banco de dados MariaDB são:

- `MARIADB_DATABASE`: Nome do banco de dados. Valor padrão: **moodledb**
- `MARIADB_USER`: Nome do usuário do banco de dados. Valor padrão: **moodledbuser**
- `MARIADB_PASSWORD`: Senha do usuário do banco de dados. Valor padrão: **moodledbpassword**

#### Contêiner do Cache (Redis)

Variáveis de ambiente suportadas pela imagem do contêiner do cache Redis são:

- `REDIS_PASSWORD`: Senha do serviço de cache. Valor padrão: **moddleredispassword**

## Serviços

- Moodle
- MariaDB
- Redis
- API de Machine-Learning

## Autores

EDUARDO COSTA BASSO

MATHEUS FELIPE KROL

## License

Copyright 2016-2021 Bitnami

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
