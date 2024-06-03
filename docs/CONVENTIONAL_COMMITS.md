[Voltar](../README.md)

# Nomenclatura de Commits

Aqui estão algumas diretrizes que usamos para padronizar nossas mensagens de commit em apenas três passos.

## Sumário:

1. [Padronização de Commit](#padronização-de-commits)
    - [Nomenclatura](#nomenclatura)
    - [Escopos](#escopo-opcional)
    - [Descrição](#descrição)
    - [Corpo](#corpo)
    - [Rodapé](#rodapé)
2. [Check-list](#check-list-de-commit)
3. [Realização de Commits](#realização-do-commit)
3. [Testando](#testando)


## Padronização de Commits

Cada commit deve seguir a estrutura simplificada do padrão Conventional Commits. 

_Estrutura básica de cada commit:_

```plaintext
<tipo>(escopo opcional): <descrição>

[link  para task no notion]
```

| _Exemplo:_
```md
feat(auth): add user authentication

[Clique aqui para acessar a Task](https://www.notion.so/g40/MARTECH-REDESIGN-WEBSITE-Mapear-eventos-do-novo-componente-de-agenda-com-galeria-accordeon--46665e4673044014a4b207b8e591c2b1)
```
## Tipos de Commit

#### Nomenclatura:

- **feat**: Nova funcionalidade para o usuário.

- **fix**: Correção de erros (bug fixes).

- **docs**: Alterações na documentação.

- **style**: Mudanças que não afetam o significado do código (formatação, falta de ponto e vírgula, etc.).

- **refactor**: Refatoração do código sem correção de bugs ou adição de funcionalidades.

- **perf**: Melhorias de desempenho.

- **test**: Adição de testes faltantes ou corrigindo testes existentes.

- **build**: Mudanças que afetam o sistema de build ou dependências externas.

- **ci**: Mudanças em arquivos e scripts de configuração de CI (Continuous Integration).

- **chore**: Atualizações de manutenção do código sem impactar o código de produção (ex.: atualizações de dependências).

- **revert**: Reversão de um commit anterior.

## Escopo (Opcional)

O escopo, que é opcional, deve ser uma palavra descrevendo a parte do código alterada (por exemplo: `auth`, `api`, `ui`).

_Exemplo:_
```plaintext
fix(api): handle user not found error
```

## Descrição

A descrição deve ser uma linha concisa explicando a alteração. Esta linha deve:
- Ser imperativa
- Não terminar com um ponto final.

_Exemplo:_

```plaintext
docs: update README with setup instructions
```

### Corpo:

- O corpo deve conter um link que redireciona a interação pra task no notion.

_Exemplo:_

```md
fix(auth): resolve issue with token validation

[Clique aqui para acessar a task]()
```

### Rodapé:

- Usado principalmente para fechar issues (e.g., Closes #123) ou mencionar breaking changes.

_Exemplo:_

```md

[Clique aqui para acessar a task]()

Closes #123
```

## Check-list de Commit

1. **Prefixo Correto**: Certifique-se de usar o prefixo correto (tipos de commit) na mensagem.

_Exemplo: `feat`, `fix`, `docs`, etc._

2. **Escopo (Opcional)**: Certifique-se de especificar a parte do código alterada (se aplicável).

_Exemplo: `feat(auth): ...`_

3. **Descrição Conisa**: A descrição deve ser clara e concisa e deve explicar a alteração de forma imperativa.

_Exemplo: `feat(auth): add user authentication`_

4. **Corpo (Opcional)**: Se necessário, adicione uma descrição detalhada no corpo do commit.

_Exemplo: `This fix ensures that...`_

5. **Rodapé (Opcional)**: Use o rodapé para fechar issues ou mencionar breaking changes.

_Exemplo: `Closes #123`_

## Realização do Commit

Para realizar seu coomit de forma padronizada, utilizamos o [Husky](), [Commitizen]() e também [CommitLint]().

Os commits devem ser realizados da seguinte forma.

```c
// Exemplo Bom
yarn commit

// Exemplo Ruim
git commit -m "Exemplo Ruim"
```

### Pronto, agora seu commit está padronizado de acordo com a documentação!

# TESTANDO

Após seguir todas as etapas, teste o commit verificando se ele aparece corretamente no histórico do GitHub. 

Certifique-se de que a mensagem do commit esteja clara e compreensível para todos os membros da equipe.

---

**_Caso tenha seguido todas as diretrizes e encontre algum problema de formatação ou consistência, envie um feedback para o time responsável._**