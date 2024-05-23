# Nomenclatura de Commits

### Aqui estão algumas diretrizes que usamos para padronizar nossas mensagens de commit em apenas três passos.

_Não há uma ordem específica, mas para fins educativos, vamos seguir os passos abaixo._

## 1.1 - Estrutura do Commit

Cada commit deve seguir a estrutura padrão do Conventional Commits. 

_Estrutura básica de cada commit:_

```plaintext

<tipo>(escopo opcional): <descrição>

[corpo opcional]

[rodapé opcional]

```

_Exemplo:_

```plaintext

feat(auth): add user authentication

Added a new user authentication feature using JWT tokens.

Closes #45

```

## 1.2 - Tipos de Commit

#### Tipos Comuns:

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

## 2.1 - Escopo (Opcional)

O escopo, que é opcional, deve ser uma palavra descrevendo a parte do código alterada (por exemplo: `auth`, `api`, `ui`).

_Exemplo:_
```plaintext
fix(api): handle user not found error
```

## 2.2 - Descrição

A descrição deve ser uma linha concisa explicando a alteração. Esta linha deve:
- Começar com letra maiúscula
- Ser imperativa
- Não terminar com um ponto final.

_Exemplo:_

```plaintext
docs: update README with setup instructions
```

## 3.0 - Corpo e Rodapé (Opcional)

### Corpo:

- O corpo deve explicar "o quê” e “por que”, de preferência evitando o "como".

- Pode ter várias linhas, com quebra de linha entre parágrafos.

_Exemplo:_

```plaintext
fix(auth): resolve issue with token validation

This fix ensures that expired tokens are handled gracefully.
The expiration time is now validated correctly, and a new custom error is thrown
when the token has expired.
```

### Rodapé:

- Usado principalmente para fechar issues (e.g., Closes #123) ou mencionar breaking changes.

_Exemplo:_

```plaintext

BREAKING CHANGE: The 'auth' module's API has been changed to accommodate new validation rules.

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

### Pronto, agora seu commit está padronizado de acordo com a documentação!

# TESTANDO

Após seguir todas as etapas, teste o commit verificando se ele aparece corretamente no histórico do GitHub. 

Certifique-se de que a mensagem do commit esteja clara e compreensível para todos os membros da equipe.

---

**_Caso tenha seguido todas as diretrizes e encontre algum problema de formatação ou consistência, envie um feedback para o time responsável._**