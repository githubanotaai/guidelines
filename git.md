# Diretrizes para utilização do Git

## GitHub

- Utilizamos Github para hospedagem do nosso código.
- Por enquanto não obrigamos autenticação por 2 fatores, mas é uma boa ideia começar a utilizar.

## Repositórios

- Só utilize repositórios públicos sob estrita necessidade.
- Utilize o nome do projeto em inglês.
- Utilize `lowercase` e `kebab-case` para nomear os repositórios.
- Se o projeto for separado por módulos, o nome deve conter 2 partes: `<projeto>-<módulo>`, deve-se utilizar um dos nomes de módulo como sufixo: `api`, `worker`, `job`, `frontend`, `dashboard`.
- Se o projeto não for separado por módulos, utilizar somente seu nome. Por exemplo: `integration`, `admin`.
- Se for utilizar repositórios para versionar o projeto, adicionar os sufixos *v1*, *v2*, etc. Por exemplo: `pizza-api-v1`.
- Exemplos de nome de repositório: `integration-api`, `intelligence-churn-analysis-job`, `integration-frontend`, `logistics-api-v2`.
- Todos repositorios devem conter um *.gitignore* ignorando arquivos temporários e binários, como `node_modules/*`.
- Todos repositórios devem conter um *README.md* com instruções básicas de uso.

## Branches

- Todos projetos devem conter uma branch *master* e *develop*.
- A branch master deve conter código estável sempre, o sistema de produção roda a partir da mesma.
- A branch develop deve conter código compilável sempre.
- Utilize `lowercase` e `kebab-case` para nomes de branch, por exemplo: `database-migration`.
- Utilize `feature/` como prefixo para branches de recursos, por exemplo: `feature/login`.
- Utilize `hotfix/` para hotfixes, por exemplo: `hotfix/failing-to-sign-up`.
- Utilize `refactor/` para refatorações, por exemplo: `refactor/user-password-reset`.
- Sempre remova branches inativas.
- Utilizamos o [Git Flow](http://nvie.com/posts/a-successful-git-branching-model/) para projetos já em produção, sendo opcional para projetos em fase inicial.

## Pull Requests

- A utilização de Pull Requests é obrigatória, não é permitido fazer o merge manual.

## Commits e Pushes

- Nunca dê commit em arquivos temporários, binários, etc.
- Cuide-se para não commitar dados sensíveis.
- Se converter um repositório privado para público, invalide os segredos (senhas de banco, AWS, etc) que já foram commitados anteriormente.
- Não utilize force push em branches estáveis, somente em branches de recurso e comunique seus colegas para evitar perda de dados.
- Procure rodar os testes localmente em vez de esperar a integração contínua.
- Quanto às mensagens de commit, recomenda-se utilizar [`Conventional Commits`](https://www.conventionalcommits.org), isso permite que ferramentas automatizadas consigam extrair dados de seus commits. (geração automática de changelogs, tags, etc.). Podem ser forçadas utilizando [`commitlint`](https://commitlint.js.org) and [`@strv/commitlint-config`](https://github.com/strvcom/code-quality-tools/tree/master/packages/commitlint-config).

## Tags

- Siga o [Semantic Versioning](https://semver.org/) para tags de versão.
- Utilize o prefixo "v", por exemplo: `v1.2.5`.
- Cada commit de release deve ter uma tag correspondente.

## Template para PRs

```markdown
## Mudanças

Explique suas mudanças.

## Links

- [Issue #123](https://link.to/jira-issue)

## Checklist

- [ ] Linter e testes passaram localmente.
- [ ] Adicionei testes que provam que meu recurso funciona e não quebra outros recursos.
- [ ] Adicionei a documentação necessária.
```
