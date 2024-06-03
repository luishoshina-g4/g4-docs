![Logo](./img/g4-banner.png)

# Documentação | g4-dinaymic-form

### Este repositório abriga a base de código do serviço de análise G4 Educação construído usando [Next.js](https://nextjs.org/blog/next-13-4) e React construído pela equipe MarTech dentro do Growth | Corporativo.

## Índices

- [Guia do Projeto](./docs/ARCHITECTURE.md)
  - [Código de Conduta](./docs/CODE_OF_CONDUCT.md)
  - [Arquitetura de Pastas](./docs/ARCHITECTURE.md#arquitetura-de-pastas)
  - [Estrutura deste Projeto](./docs/ARCHITECTURE.md#estrutura-do-projeto)

- [Estruturação dos Componentes](./docs/COMPONENT_STRUCTURE.md)
  - [Estrutura de componentes](./docs/COMPONENT_STRUCTURE.md#estrutura-de-componentes)
  - [Criando componentes](./docs/COMPONENT_STRUCTURE.md#criando-componentes)
  - [Exportando arquivos](./docs/COMPONENT_STRUCTURE.md#exportando-arquivos)
  - [Custom hooks](./docs/COMPONENT_STRUCTURE.md#custom-hooks)
  - [Componentes em PascalCase](./docs/COMPONENT_STRUCTURE.md#componentes-em-pascalcase)
  - [Nomeando arquivos](./docs/COMPONENT_STRUCTURE.md#nomeando-coisas)
  - [Class Component](./docs/COMPONENT_STRUCTURE.md#class-component)

- [Guia de Estilizações](#geral)
  - [Estilizando componentes](./docs/STYLEGUIDE.md#estilizando-componentes)
  - [Tipando componentes](./docs/STYLEGUIDE.md#tipando-componentes)
  - [Alt em imagens](./docs/STYLEGUIDE.md#alt-em-imagens)

- [Manutenção](#manutenção)
  - [Testes Unitários](./docs/UNITS_TESTS.md)
  - [Convenção de Commits](./docs/CONVENTIONAL_COMMITS.md)
  - [Versionamento de Código](./docs//CODE_VERSIONING.md)

## Geral

### Início Rápido (Ambiente Desenvolvimento)

1. Primeiramente, recupere e adicione as variáveis obrigatórias no .env

```
  > NEXT_PUBLIC_AWS_ACCESS_KEY_ID=
  > NEXT_PUBLIC_AWS_SECRET_ACCESS_KEY=
  > NEXT_PUBLIC_AWS_DB_SCHEMAS=
  > NEXT_PUBLIC_AWS_DB_EVENTS=
  > NEXT_PUBLIC_API_URL=
  > NEXT_PUBLIC_API_TOKEN=
```

1. Para este projeto, você deve rodar os seguintes comandos:

```sh
yarn && yarn dev
```

2. Abra [localhost:3000](http://localhost:3000) para ver em ação.

## Commits

Para realizar commits e enviar Pull Request's, [leia aqui](/docs/CONVENTIONAL_COMMITS.md)