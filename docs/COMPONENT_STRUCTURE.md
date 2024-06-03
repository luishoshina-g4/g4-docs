[Voltar](../README.md)

# Guia de Componentes

Referências de estruturação com os patterns utilizados no `Google JavaScript Style Guide`.

1.  [Estrutura de componentes](#estrutura-de-componentes)
2.  [Criando componentes](#criando-componentes)
3.  [Exportando arquivos](#exportando-arquivos)
4.  [Custom hooks](#custom-hooks)
5.  [Componentes em PascalCase](#componentes-em-pascalcase)
6.  [Nomeando arquivos](#nomeando-coisas)
7.  [Class Component](#class-component)

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
