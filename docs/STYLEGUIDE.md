[Voltar](../README.md)

# Guia de Desenvolvimento

Referência de estilos com os patterns utilizados no `Google JavaScript Style Guide`

- [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)

## Sumário:

1.  [Regras básicas](#regras-básicas)
2.  [Estrutura de componentes](#estrutura-de-componentes)
3.  [Criando componentes](#criando-componentes)
4.  [Exportando arquivos](#exportando-arquivos)
5.  [Custom hooks](#custom-hooks)
6.  [Arquivos em PascalCase](#arquivos-em-pascalcase)
7.  [Nomeando arquivos](#nomeando-coisas)
8.  [Class Component](#class-component)
9.  [Estilizando componentes](#estilizando-componentes)
10. [Tipando componentes](#tipando-componentes)
11. [Alt em imagens](#alt-em-imagens)
12. [Estruturas de pastas](#estrutura-de-pastas)

## Regras básicas

- Um componente por arquivo
- Não use `any` nas tipagens
- Componentes unicamente em TSX
- Código apenas em inglês

  > `Por mais que a maioria de nós de MarTech sejamos brasileiros é importante padronizarmos todo o código em inglês para evitar uma possível confusão...`
  
  > `um dos principais motivos também é a acessibilidade, muitas ferramentas de tradução automática e leitores de tela são mais eficazes quando lidam com texto em inglês.`

## Estrutura de componentes

Este projeto está usando o pattern `Atomic Design` para components.

```
┣ 📂 components
┃  ┣ 📂 atoms
┃  ┣ 📂 molecules
┃  ┣ 📂 organisms
┃  ┗ 📂 templates
```

- Separe a pasta do seu componente em 4 arquivos
  - Componente.spec.tsx (testes do componente)
  - Componente.tsx (seu componente em si)
  - Componente.types.ts (interfaces e types do componente)

```
┣ 📂 component
┃  ┣ MyComponent.spec.tsx
┃  ┣ MyComponent.tsx
┃  ┗ MyComponent.types.ts
```

[Voltar ao Sumário](#sumário)

## Criando componentes

Todos os componentes serão criados em **`funções normais`**.

> `arrow functions` **apenas** dentro dos componentes

```typescript
// Bom
function Component(props: IProps) {
	const handleSomething = () => { /* ... */ }
	return ( /* ... */ )
}

// Ruim
const Component = (props: IProps) => {
	const handleSomething = () => { /* ... */ }
	return ( /* ... */ )
}

// Ruim
const Component = (props: IProps) => {
	function handleSomething() { /* ... */ }
	return ( /* ... */ )
}
```

## Exportando arquivos

Iremos usar **SEMPRE** `export default` nos componentes

```typescript
// Bom
function Component(props: IProps) {
	return ( /* ... */ )
}

export default Component

// Ruim
export function Component(props: IProps) {
	return ( /* ... */ )
}

// Ruim
function Component(props: IProps) {
	const handleSomething = () => { /* ... */ }
	return ( /* ... */ )
}
```

Com excessão dos componentes, não iremos usar export default

```typescript
// Bom
export interface IProps {
  /* ... */
}

// Ruim
interface IProps {
  /* ... */
}
export default IProps;
```

Isso também vale para `custom hooks`

```typescript
// Bom
export const useHook = () => {
  /* ... */
};

// Ruim
const useHook = () => {
  /* ... */
};

export default useHook;
```

## Custom hooks

Se precisar criar um custom hook, use `arrow functions`

```typescript
// Bom
export const useHook = () => {
  /* ... */
};

// Ruim
export function useHook() {
  /* ... */
}
```

## Componentes em PascalCase

Iremos seguir o padrão PascalCase que consiste em nomear todas as palavras com a primeira letra maiúscula.

```
┣ 📂 component
┃  ┣ MyComponentHere.tsx
```

## Nomeando coisas

Tirando componentes e interfaces, iremos utilizar `camelCase` para nomear tudo.

```typescript
// Bom
const handleSomething = () => {
  /* ... */
};

// Ruim
const HandleSomething = () => {
  /* ... */
};

// Ruim
const handle_something = () => {
  /* ... */
};
```

Isso Inclue props de componentes

```tsx
<MyComponent
	isHandsome
	name="hxsggsz"
/>
```

Se a prop é uma string sempre passe entre aspas, única excessão é se você for usar `template string`

```tsx
// Bom
<MyComponent
	isHandsome
	name="hxsggsz"
/>

// Ruim
<MyComponent
	isHandsome
	name={"hxsggsz"}
/>
```

Oculte parâmetros que sempre serão `true`

```typescript
// Bom
<button isLoading>teste<button>

// Ruim
<button isLoading={true}>teste<button>
```

## Class component

Nosso projeto está sendo feito inteiramente com `programação funcional`, então apenas use `functional components` _(salvo excessões bem excessíveis)_:

```typescript
// Bom
function Component(props: IProps) { /* ... */ }

export default Component

// Ruim
class Component extends React.Component {
  // ...
  render() {
    return ( /* ... */ )
  }
}
```

## Estilizando componentes

Estamos utilizando `tailwind.css` para estilização

A abordagem `Concentric CSS` funciona bem com classes utilitárias, ou seja...
  - posicionamento/visibilidade
  - modelo da caixa
  - bordas
  - fundos 
  - tipografia 
  - ... outros ajustes visuais
  
Uma vez que estabelecemos essa ordem, analisar string longas de classes utilitárias analisar o código se torna muito mais rápido e fluido, então um pouco mais de esforço inicial vale a pena!

Sempre use menos classes utilitárias quando possível.

```tsx
 // Bom
 <div class="mx-2">Exemplo Bom</div>

 // Ruim
 <div class="ml-2 mr-2">Exemplo Ruim</div>
```

Prefixe todas as classes utilitárias que se aplicam apenas a um determinado ponto de interrupção com o prefixo desse ponto de interrupção. 

```tsx
  // Bom
  <div class="block lg:flex lg:flex-col lg:justify-center">Exemplo Bom</div>
  
  // Ruim
  <div class="block lg:flex flex-col justify-center">Exemplo Ruim</div>
```

Assim fica muito claro que as utilidades de flexbox se aplicam apenas no ponto de interrupção `lg:` e superior.

_(Lembre-se de que, por padrão, todas as utilidades responsivas são configuradas para se aplicarem a partir da largura mínima.)_

```tsx
// Bom
<div class="block md:flex">Exemplo Bom</div>

// Ruim
<div class="block md:flex xl:flex">Exemplo Ruim</div>
```

Também observe que, por padrão, o ponto de interrupção `sm:` não começa em `min-width: 0`, como você poderia esperar. 

#### Ele começa em `min-width: 640px`. 

Portanto, se você quiser que algo se aplique apenas para as menores visualizações, você deve primeiro configurá-lo para aplicar a todos os pontos de interrupção e depois substituí-lo para pontos de interrupção maiores.

> Se você quiser que algo apareça como block apenas para as menores telas

```tsx
 <div class="sm:inline">Exemplo</div>
```

### Classes de componentes

Não use `@apply` prematuramente para abstrair classes de componentes onde um componente adequado baseado em framework/modelo é mais apropriado. 

No entanto, se a string de classes utilitárias dentro desse componente também for usada em outros componentes, então há uma verdadeira duplicação. 

Nesse caso, a criação de uma nova classe de componente CSS compartilhada com @apply pode ser justificada.

> Não use @apply em classes de componentes em outros componentes. Por exemplo, mantenha classes separadas .btn e .btn-blue em vez de usar .btn-blue { @apply btn; }

### Classes dinâmicas

Quando classes CSS são selecionadas ou geradas dinamicamente, não use concatenação de string para combinar fragmentos da classe completa. Em vez disso, alterne entre as strings completas.

Você sempre deve querer a string completa de cada classe utilitária presente na marcação para facilitar o raciocínio e garantir que ela sobreviva ao processo `PurgeCSS`.

_Existem excessões em que é precisa usar `inline styles`, mas são casos específicos e estarão atrelados a apenas uma propriedade!_

## Tipando componentes

Priorize `Interfaces` no lugar de `Types` , ambos servem para fazer a mesma coisa, mas estamos seguindo o padrão de interfaces

```ts
// Bom
interface IProps {
  /* ... */
}

// Ruim
type IProps = {
  /* ... */
};
```

Use o Prefixo `I` na hora da criação de interfaces.

```ts
// Bom
interface IProps {
  /* ... */
}

// Ruim
interface PropTypes {
  /* ... */
}
```

Use o Prefixo `T` na hora da criação de tipos.

```ts
// Bom
type TProps = {
  /* ... */
};

// Ruim
type PropTypes = {
  /* ... */
};
```

Use o Prefixo `E` na hora da criação de enums.

```ts
// Bom
enum ECoisas = { /* ... */ }

// Ruim
type Coisas = { /* ... */ }
```

## Alt em imagens

SEMPRE coloque o atributo `alt` quando for usar alguma imagem no projeto, é bom por causa do `SEO` (mesmo que esse projeto não seja web) e acessibilidade.

```tsx
// Bom
<img src={image} alt="me and my dog" />

// Ruim
<img src={image} />
```

Evite usar o prefixo `image` ou `picture` porque os leitores de tela ja adicionam esse prefixo na hora de ler o `alt` então ficaria duplicado

```tsx
// Ruim
<img src={image} alt="image about me and my dog" />
```

## Estrutura de pastas do projeto

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
