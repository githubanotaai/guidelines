# Diretrizes para utilização do Git

## GitHub

- Utilizamos Github para hospedagem do nosso código.
- Por enquanto não obrigamos autenticação por 2 fatores, mas é uma boa ideia começar a utilizar.

## Definições

- projeto: produto da anota ai
- módulo: componente de um produto, por exemplo `api`, `frontend` e `worker`.

## Repositórios

- Só utilize repositórios públicos sob estrita necessidade.
- Utilize o nome do projeto em inglês.
- Utilize `lowercase` e `kebab-case` para nomear os repositórios.
- Caso o projeto contenha mais de uma palavra utilize as mesmas regras de nomenclatura.
- Se o projeto for separado por módulos, o nome deve conter 2 partes: `<projeto>-<módulo>`, nomes de módulo sugeridos são: `api`, `worker`, `job` e `front`.
- Se o projeto não for separado por módulos, utilizar somente seu nome. Por exemplo: `integration-dashboard`, `intelligence-reports`.
- Se for utilizar repositórios para versionar o projeto, adicionar os sufixos *v1*, *v2*, etc. Por exemplo: `pizza-api-v1`.
- Exemplos utilizando o projeto "intelligence": `intelligence-api`, `intelligence-analytics-worker`, `intelligence-admin`.
- Exemplos utilizando o projeto "integration-partner-admin": `integration-partner-admin-api`, `integration-partner-admin-front`.
- Todos repositorios devem conter um *.gitignore* ignorando arquivos temporários e binários, como `node_modules/*`.
- Arquivos como `package.json` e `package-lock.json` devem ser versionados.
- Todos repositórios devem conter um *README.md* com instruções básicas de uso.

## Branches

- Todos projetos devem conter uma branch *master* e *develop*.
- A branch master deve conter código estável sempre, o sistema de produção roda a partir da mesma.
- A branch develop deve conter código compilável sempre, o sistema de staging roda a partir da mesma.
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
- Se converter um repositório privado para público, não se esqueça de invalidar os segredos (senhas de banco, AWS, etc) se já foram commitados anteriormente.
- É importante versionar lock files como `package-lock.json`, nos permite manter versões exatas das nossas dependências.
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
