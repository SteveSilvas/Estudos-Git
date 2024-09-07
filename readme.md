# TUTORIAL GIT

Este tutorial fornece uma visão geral dos principais comandos Git utilizados no controle de versão de projetos.

## ▪ Inicializando um Repositório Git
### `git init`
O comando `git init` cria um novo repositório Git em um diretório existente. Ele inicializa a pasta `.git`, onde o Git armazenará seus metadados e histórico.

```bash
git init
```

* **Descrição**: Inicia um repositório Git.
* **Uso comum**: Criação de um novo projeto versionado ou configuração de Git em um projeto existente.


## ▪ Adicionando Origem Remota a um Repositório Git
### `git remote add origin URL_DO_REPOSITORIO`
Vincula um repositório local a um repositório remoto associando as branchs exitentes em ambos.

```bash
git remote add origin https://github.com/usuario/repositorio.git
```

* **Descrição**: Adiciona a URL do repositório remoto como origem (normalmente chamado de origin).
* **Uso comum**: Quando você cria um repositório local e deseja associá-lo a um repositório remoto.

Depois de adicionar a origem remota, você pode verificar a configuração com:
```bash
git remote -v
```
Isso exibirá as URLs associadas ao seu repositório remoto para fetch (busca) e push (envio).


## ▪ Baixando um Repositório Remoto
### `git clone <url>`
Faz o clone de um repositório remoto para a máquina local.

```bash
git clone https://github.com/usuario/repo.git
```

* **Descrição**: Cria uma cópia local de um repositório remoto.
* **Uso comum**: Obter uma cópia de trabalho de um repositório Git hospedado remotamente.

## ▪ Visualizando o Status do Repositório

### `git status`
Mostra o status atual do repositório, incluindo arquivos modificados, arquivos em staging e aqueles que não estão sendo rastreados.

```bash
git status
```

* **Descrição**: Verifica o status atual dos arquivos no repositório.
* **Uso comum**: Verificar o que mudou ou está pronto para commit.


## ▪ Visualizando o Histórico de Commits
### `git log`
Mostra o histórico de commits do repositório, incluindo hash, autor, data e mensagem de cada commit.

```bash
git log
```

* **Descrição**: Exibe o histórico de commits.
* **Uso comum**: Analisar o histórico de versões.

## ▪ Adicionando Arquivos ao Staging

### `git add <arquivo>`
Adiciona arquivos específicos ao estágio (ou staging area) para que possam ser confirmados em um commit.

```bash
git add nome-do-arquivo
```

* **Descrição**: Prepara arquivos para commit.
* **Uso comum**: Adicionar arquivos alterados ou novos para serem incluídos no próximo commit.


## ▪ Adicionando TODOS os Arquivos Modificados ao Staging
### `git add .`
Adiciona arquivos específicos ao estágio (ou staging area) para que possam ser confirmados em um commit.

```bash
git add nome-do-arquivo
```

* **Descrição**: Prepara arquivos para commit.
* **Uso comum**: Adicionar arquivos alterados ou novos para serem incluídos no próximo commit.


## ▪ Criando um Commit
### `git commit -m "<mensagem>"`
Faz o commit das mudanças que foram adicionadas ao estágio, criando um ponto no histórico de versões do projeto.

```bash
git commit -m "Mensagem clara do que foi alterado"
```

* **Descrição**: Cria um novo commit no histórico.
* **Uso comum**: Confirmar mudanças no código com uma descrição.


## ▪ Atualizando o Local com o Repositório Remoto
### `git pull origin <branch>`
Faz o clone de um repositório remoto para a máquina local.

```bash
git pull origin <branch>
```

* **Descrição**: Sincroniza o repositório local com as últimas alterações da branch remota.
* **Uso comum**:  Trazer mudanças atualizadas de outros colaboradores.


## ▪ Enviando Alterações para o Repositório Remoto
### `git push origin <branch>`
Faz o clone de um repositório remoto para a máquina local.

```bash
git push origin dev
```
ou
```
git push
```

* **Descrição**:  Envia suas alterações de commits para o servidor remoto.
* **Uso comum**:  Compartilhar seu trabalho com outros desenvolvedores e hospedar na nuvem os commits realizados localmente.


## ▪ Enviando Alterações para o Repositório Remoto informando qual a branch associar
### ` git push --set-upstream origin <branch-remota-associada>`
Este comando envia as alterações dos commits da branch local atual para a branch remota especificada, além de definir uma associação entre a branch local e a remota, facilitando futuros pushes sem a necessidade de especificar a branch remota novamente.
```bash
 git push --set-upstream origin master
```

* **Descrição**: Envia as alterações da branch local para a branch remota e estabelece um relacionamento entre as duas, permitindo que os próximos comandos git push usem esse link automaticamente.
* **Uso comum**: Quando você cria uma nova branch local e deseja associá-la a uma branch remota pela primeira vez, evitando a necessidade de especificar a branch remota em comandos subsequentes de push.


## ▪ Rebasing (Reorganizando o Histórico de Commits)
### `git rebase <branch>`
Este comando aplica as mudanças da branch dev na branch atual, reescrevendo o histórico.

```bash
git rebase dev
```
ou
```
git rebase origin dev
```

* **Descrição**: Integra as mudanças da branch dev na branch atual.
**Uso comum**: Atualizar a branch de trabalho com as últimas mudanças de outra branch, como dev, sem criar commits de merge.


## ▪ Rebasing (Mantendo o Histórico de atual)
### `git rebase <branch> --ours`
Aplica as mudanças da branch dev na branch atual e, em caso de conflito, aceita as mudanças da branch atual, sobrescrevendo o que veio de dev.

```bash
git rebase dev --ours
```

* **Descrição**: Atualiza a branch atual com base em dev, mas, em caso de conflitos, mantém as alterações da branch atual.
**Uso comum**: Usado quando deseja-se preservar completamente as mudanças locais.

## ▪ Rebasing (Mantendo o Histórico que está vindo)
### `git rebase --strategy-option=theirs`
Aplica as mudanças da branch dev na branch atual e, em caso de conflito, aceita as mudanças origem, sobrescrevendo o local.

```bash
git rebase origin dev --strategy-option=theirs
```

* **Descrição**: Atualiza a branch atual com base em dev, mas, em caso de conflitos, mantém as alterações da branch de origem descartando as mudanças atuais
**Uso comum**: Usado quando deseja-se preservar completamente as mudanças remotas sobrescrevendo a brancha tual.

## ▪ Criando Ramificações/Branches
### `git branch <nome-da-branch>`
Cria uma nova ramificação/branch no repositório atual.

```bash
git branch minha-branch
```

* **Descrição**: Cria uma nova ramificação (branch) no código possibilitando o desenvolvimento de uma versão do projeto independente das demais ramificações.
**Uso comum**: Separar o desenvolvimento de novas funcionalidades ou correções de bugs em branches diferentes.


## ▪ Trocar de Ramificações/Branches
### `git checkout <nome-da-branch-existente>`
Muda para uma branch existente.

```bash
git checkout nome-da-branch-existente
```

* **Descrição**: Troca a versão dos arquivos do repositório para outra branch.
**Uso comum**: Alternar entre diferentes linhas de desenvolvimento.

## ▪ Criar e mudar para uma nova branch ao mesmo tempo
### `git checkout -b <nome-da-nova-branch>`
Cria e Muda para uma branch.

```bash
git checkout -b nome-da-nova-branch
```

* **Descrição**: Cria uma nova ramificação e altera a versão dos arquivos para ela. Por não passar qual a branch na qual foi baseada ela será gerada a partir da branch atual.
**Uso comum**: Criar uma branch para trabalho imediato.


## ▪ Mesclar Branches
### `git merge <branch>`
Faz a junção de uma branch especificada com a branch atual.

```bash
git merge nome-da-branch
```

* **Descrição**: Mescla as alterações de outra branch na branch atual.
**Uso comum**: Juntar o desenvolvimento de duas branches após a finalização de uma funcionalidade.


## ▪ Lidando com Conflitos
##### Durante um rebase, pull ou merge, podem ocorrer conflitos. Nesse caso, o Git marcará os arquivos com conflitos e o desenvolvedor precisará resolvê-los manualmente.
Faz a junção de uma branch especificada com a branch atual.

```bash
git merge nome-da-branch
```

* **Descrição**: Mescla as alterações de outra branch na branch atual.
**Uso comum**: Juntar o desenvolvimento de duas branches após a finalização de uma funcionalidade.

1 - Edite os arquivos com conflito.
2 - Marque os arquivos como resolvidos:
```bash
git add arquivo-com-conflito
```
ou 
```bash
git add .
# Para adicionar todos os arquivos modificados para o próximo commit
```
3- Continue o processo de rebase ou merge:

```bash
git rebase --continue
```
ou 
```bash
git merge --continue
```

4- Caso queira abortar o processo de rebase ou merge:

```bash
git rebase --abort
```
ou 
```bash
git merge --abort
```

## ▪ Enviando Alterações para o Repositório Remoto informando qual a branch associar
### `git pull origin <branch> --allow-unrelated-histories`
Este comando faz o pull das alterações da branch remota especificada para a branch local atual, mesmo que os históricos de commits entre os dois repositórios não estejam relacionados. Isso é útil quando você está tentando combinar dois repositórios que foram inicializados separadamente ou têm históricos divergentes.
```bash
git pull origin main --allow-unrelated-histories
```

* **Descrição**: Permite combinar um repositório remoto com um local que possui históricos de commits diferentes, forçando a união entre eles.
* **Uso comum**: Quando você está trabalhando com dois repositórios que foram criados separadamente e precisa unir as histórias sem a rejeição comum de "histórias não relacionadas".


## ▪ Ignorando Arquivos com .gitignore
### `Crie um arquivo e salve com o nome  .gitignore`
O arquivo .gitignore é usado para listar arquivos e diretórios que o Git deve ignorar, como arquivos de senhas e chaves de apis, arquivos temporários, binários, etc.
Exemplo de um arquivo .gitignore:
```bash
# Ignora arquivos de log
*.log

# Ignora diretórios de build
/build/
```

* **Descrição**: Permite a configuração de arquivos ou pastas que não serão versionados, ou seja, não estarão disponíveis no diretório remoto e nem terão suas versões acompanhadas pelo git.
**Uso comum**: Excluir pastas de dependências como node_modules par não sobrecarregar o repositório remoto com arquivos úteis apenas durante a execução do projeto, ocultar arquivos com chaves e dados sigilosos.


## ▪ Desfazendo Alterações
### `git reset --hard <commit>`
Reverte o repositório para um commit anterior, removendo todas as alterações não confirmadas.
```bash
git reset --hard <hash-do-commit>
```

* **Descrição**: Restaura o estado do repositório para um commit anterior.
**Uso comum**: Descartar alterações feitas após um commit específico.

