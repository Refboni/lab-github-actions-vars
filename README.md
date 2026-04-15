# Lab: GitHub Actions Variables (CTT10)

Este repositório contém a resolução do exercício prático sobre variáveis e escopos no GitHub Actions.

## Respostas de Reflexão

### 1. Por que a variável `STEP_TEMP` não apareceu no Passo 2?
Porque ela foi definida dentro do escopo local do Passo 1. No GitHub Actions, variáveis de ambiente definidas em um `step` são isoladas e não ficam disponíveis para outros steps, a menos que sejam exportadas para o arquivo global `$GITHUB_ENV`.

### 2. Qual a diferença entre usar `$VAR` e `${{ vars.VAR }}`?
- `$VAR` (ou `$APP_NAME`) é usado dentro de comandos shell (Bash) para acessar variáveis de ambiente que já estão carregadas no sistema.
- `${{ vars.VAR }}` ou `${{ secrets.VAR }}` é a sintaxe do GitHub Actions (Contexts) usada para buscar valores que estão guardados fora do código, nas configurações do repositório.

### 3. Por que o token apareceu como `***` no log?
Por segurança. O GitHub identifica automaticamente quando um valor vindo de um `Secret` é impresso no terminal e o mascara com asteriscos para evitar que senhas e credenciais fiquem expostas nos logs públicos.
