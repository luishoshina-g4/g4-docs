[Voltar](../README.md)

## Arquitetura de Pastas

Este projeto está usando o pattern `Atomic Design` para components.

```
┣ 📂 components
┃  ┣ 📂 atoms
┃  ┣ 📂 molecules
┃  ┣ 📂 organisms
┃  ┗ 📂 templates
```

- Separe a pasta do seu componente em 4 arquivos
  - Componente.spec.tsx ([testes do componente](./UNITS_TESTS.md))
  - Componente.tsx (seu componente em si)
  - Componente.types.ts (interfaces e types do componente)

```
┣ 📂 component
┃  ┣ MyComponent.spec.tsx
┃  ┣ MyComponent.tsx
┃  ┗ MyComponent.types.ts
```

## Estrutura do Projeto

```
    📦 g4-dinamyc-form
    ┣ 📂 public
    ┃ ┗  arquivos publicos como robots.txt, favicons, sitemap.xml e etc.
    ┣ 📂 src
    ┃ ┣ 📂 api | requisições da aplicação.
    ┃ ┣ 📂 app | pasta principal da aplicação.
    ┃ ┣ 📂 assets
    ┃ ┃ ┣ 📂 icons
    ┃ ┃ ┣ 📂 images
    ┃ ┣ 📂 components
    ┃ ┃ ┣ 📂 atoms | componentes básicos, pequenos e isolados unicamente.
    ┃ ┃ ┣ 📂 molecules | componentes simples apartir da pasta `atoms`.
    ┃ ┃ ┣ 📂 organisms | componentes que podem ser utilizados pra construir interfaces.
    ┃ ┃ ┣ 📂 templates | componentes páginas.
    ┃ ┃ 📂 constants | constantes que não são relativas a um módulo específico
    ┃ ┃ 📂 context | gerenciamento e compartilhamento de estados globais
    ┃ ┃ 📂 enum | conjunto finito de valores unicos da aplicação
    ┃ ┃ 📂 utils | funções/classes de alta usabilidade
```