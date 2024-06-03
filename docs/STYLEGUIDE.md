[Voltar](../README.md)

# Guia de Estilizações

Referência de estilos com os patterns utilizados no `Google JavaScript Style Guide`

- [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)

## Sumário:

2. [Estilizando componentes](#estilizando-componentes)
3. [Tipando componentes](#tipando-componentes)
4. [Alt em imagens](#alt-em-imagens)
5. [Estruturas de pastas](#estrutura-de-pastas)

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