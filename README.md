![Logo](https://scontent.fcgh9-1.fna.fbcdn.net/v/t39.30808-6/354037739_1150873909138616_5563000492426352288_n.png?_nc_cat=102&ccb=1-7&_nc_sid=5f2048&_nc_ohc=Y939xgeWdBkQ7kNvgHBM1xf&_nc_ht=scontent.fcgh9-1.fna&oh=00_AYAXwtdNpSRor0KbztOOZKgAjpwsF4_icw9qYXLUUOND-g&oe=6654760E)

# Documentação

## Índice

- [Geral](#geral)

  - [Comandos CLI](#comandos-cli)

  - [Introdução](#introdução)

  - [Configuração de Ferramentas](#configuração-de-ferramentas)

  - [Configurações do Servidor](#configurações-do-servidor)

  - [Debug](#debug)

  - [FAQ](#faq)

  - [Dicas](#dicas)

  - [Remoção](#remoção)

  - [Extração de Componentes](#extração-de-componentes)

- [Testes](#testes)

  - [Testes Unitários](#testes-unitários)

  - [Testes de Componentes](#testes-de-componentes)

  - [Testes Remotos](#testes-remotos)

- [Estilização (CSS)](#estilização-css)

  - [CSS de Nova Geração](#css-de-nova-geração)

  - [Suporte a CSS](#suporte-a-css)

  - [Folha de Estilos](#folha-de-estilos)

  - [Módulos CSS](#módulos-css)

  - [Sass](#sass)

  - [LESS](#less)

- [JavaScript](#javascript)

  - [Roteamento](#roteamento)

- [Manutenção](#manutenção)

  - [Atualização de Dependências](#atualização-de-dependências)

## Visão Geral

### Início Rápido (Ambiente Desenvolvimento)

1. Para este projeto, você deve rodar os seguintes comandos:

```sh
yarn && yarn dev
```

2. Abra [localhost:3000](http://localhost:3000) para ver em ação.

### Estrutura

O diretório [`app/`](../../../tree/master/app) contém todo o código da sua aplicação, incluindo CSS, JavaScript, HTML e testes.

O resto das pastas e arquivos só existem para facilitar a escalabilidade e não devem ser alterados.

_(Se precisarem ser alterados, por favor, [envie um slack]())_

### Testes

Para uma explicação detalhada do procedimento de testes, veja a [documentação de testes](./testing/README.md)!

#### Testes de Navegador

`npm run start:tunnel` torna sua aplicação localmente executada acessível globalmente na web via uma URL temporária: ótimo para testar em diferentes dispositivos, demos para clientes, etc!

#### Testes Unitários

Os testes unitários ficam em diretórios `test/` logo ao lado dos componentes sendo testados e são executados com `npm run test`