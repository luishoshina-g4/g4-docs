[Voltar](../README.md)

# Testes unitários

Tente ser o mais claro para descrever seus testes, descreva a ação que você vai fazer como `describe()` e use o `it()` para descrever a ação esperada do teste. Siga esse padrão:
_Evite a palavra "should" seguida do `it`, faça sua sentença ser hiperativa, como "it has", "it renders", "it fails" e etc. Isso serve pra evitar que toda descrição de um teste inicie por "should"._

```ts
describe('MyButtonComponent', () => {
  describe('when initialize', () => {
    it('shows the button on screen', () => {
      // ...
    });

    describe('when click', () => {
      it('calls the handleButton function ', () => {
        // ...
      });
    });
  });
});
```