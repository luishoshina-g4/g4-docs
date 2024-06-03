[Voltar](../README.md)

# Versionamento de Código

Aqui estão algumas boas práticas que seguem nossa padronização para versionamento de código.

## Sumário:

1. [Versionamento de Código](#versionamento-de-código)
    - [Git Flow](#git-flow)
    - [Branchs](#branching)
2. [Pull Request](#pull-request)
    - [Criando um Pull Request](#criando-um-pull-request)
    - [Revisão de Código](#revisão-de-código)
    - [Boas Práticas para Pull Requests](#boas-práticas-para-pull-requests)
3. [Contribuindo para o Projeto](#contribuindo-para-o-projeto)

## Templates de PR's

Cada PR deve conter a seguinte estrutura simplificada que segue nosso padrão.

## Git Flow

Git Flow é um modelo de branching para git que define um fluxo de trabalho robusto para gestão de releases e desenvolvimento contínuo.

Principais branches:
- `main`: Contém o histórico de lançamentos oficiais.
- `hotfix/*`: Correção de bugs em produção.
- `release/*`: Preparação de uma nova release.
- `develop`: Funcionalidade em desenvolvimento, pré-release.
- `feature/*`: Funcionalidade em desenvolvimento específica.

![GitFlow](https://raw.githubusercontent.com/gist/CisinoJr/dae76fbfac1262b67d33e400e5285d58/raw/c63a21daf1610c5f2834e19a5e8e7ec37a569fda/gitflow.png)

### Branching

O uso de branches vai facilitar nosso trabalho em diferentes funcionalidades e correções de forma isolada antes de mesclar as alterações de volta a branch principal.

Exemplo de branches:
- `feature/user-authentication`
- `hotfix/login-issue`

## Pull Request

### Criando um Pull Request

1. **Crie um Branch:**
   ```bash
   git checkout -b feature/minha-funcionalidade
   ```
2. **Faça commits das suas alterações:**
   Leia a seção de [Padronização de Commits](./CONVENTIONAL_COMMITS.md)

3. **Suba o branch para o repositório remoto:**
   ```bash
   git push origin feature/minha-funcionalidade
   ```
4. **Abra um Pull Request no repositório remoto:** 
   - Vá até o repositório no GitHub.
   - Clique em "New Pull Request" ou "Compare & Pull Request".
   - Escolha o branch que você deseja mesclar e conclua a criação do PR.

### Revisão de Código

O code review em cada PR é uma etapa muito importante, e nossos PR's são aprovados com 2 aprovações.

- **Revisores**: Geralmente dois membros do time.
- **Comentários e Feedback**: Revise, comente e solicite mudanças, se necessário.
- **Aprovação**: Após as correções e validações, o PR pode ser aprovado e mesclado.

### Boas Práticas para Pull Requests

- **Descrição Clara**: Sempre forneça uma descrição clara das alterações realizadas.
- **Commits Pequenos e Concisos**: Mantenha os commits pequenos e específicos.
- **Documentação Atualizada**: Atualize documentação relevante junto com as alterações de código.
- **Testes**: Inclua testes automatizados para suas alterações.

## Contribuindo para o Projeto

Para contribuir ao projeto, siga estas etapas:

1. **Clone o repositório para o seu ambiente local:**
    ```bash
    git clone https://github.com/usuario/repo.git
    ```
2. **Crie um branch para sua feature ou correção:**
    ```bash
    git checkout -b feature/minha-feature
    ```
3. **Faça suas mudanças e faça commit delas:**

    Leia o tópico de [Convenção de Commits](./CONVENTIONAL_COMMITS.md)
4. **Envie suas mudanças para o repositório remoto:**
    ```bash
    git push origin feature/minha-feature
    ```
5. **Abra um Pull Request** para revisão de suas mudanças.