# Comandos e Instruções - Curso de Git e GitHub

texto inicial

## Comandos no Terminal do Repositório Local


### Verificar a Versão do Git

    git --version


### Criar novo repositório

    git init

### Verificar estado dos arquivos/diretórios

    git status

---
***

### *Comandos para Stage - arquivo/diretório*    

**Stage (área de preparação):** Também conhecida como "staging area" ou "index“ é onde as modificações nos arquivos são selecionadas para serem incluídas no próximo commit.


**Ação**                         |**Comando** 
---                          |---
Adicionar um arquivo        :| ``` git add meu-arquivo.ext        ```
Remover   um arquivo        :| ``` git rm --cache meu-arquivo.ext ```
Adicionar um diretorio      :| ``` git add meu-diretorio          ```
Remover   um diretorio      :| ``` git rm --cache meu-diretorio   ```
Adicionar todos os arquivos :| ``` git add .                      ```

### *Comandos Commits - arquivo/diretório*  

**Commit (Confirmar):** É uma operação que registra as alterações realizadas nos arquivos incluídos na área de preparação. Ele cria um ponto de referência na história do repositório.

**Ação**                         |**Comando** 
---                          |---
Commit                      :| ``` git commit - m "Mensagem do Commit"                 ```
Commit + (nome do arquvio)  :| ``` git commit meu-arquivo.ext - m "Mensagem do Commit" ```
Commit varios Arquivos      :| ``` git commit meu-arquivo.txt meu-arquivo-2.txt        ```
Commit + Editor de Texto    :| ``` git commit + tecla enter                            ```   

#### Comando Para Adição no Staged e Commit

    git commit -am "Mensagem do Commit"

***
---

### *Logs*

**Logs (Registros):** Referem-se aos registros de eventos ou informações relevantes que são registrados por um sistema ou aplicativo. Esses registros são geralmente armazenados em arquivos de log, que registram atividades específicas ocorridas durante a execução de um programa, sistema operacional, serviço da web ou qualquer outro sistema de software.

**Ação**                       |**Comando** 
---                            |---
Logs dos Commit               :| ``` git log                         ```
Logs dos Commits específicos  :| ``` git log -n (numero de commits)  ```
Logs dos Commits resumido     :| ``` git log --oneline               ```
Logs dos Commits alterações   :| ``` git log --stat                  ```


**Obs: Fazer junção dos git log**  Ex: ` git log -n 3 --oneline `

### *Restore*

**Git Restore:** É um comando do Git que permite desfazer modificações em arquivos do repositório. Ele permite reverter alterações em arquivos modificados ou até mesmo restaurar arquivos excluídos.

#### Restaurar um arquivo deletado:

    git restore meu-arquivo.ext

#### Restaurar arquivo modificado: 

    git checkout 

#### Restaurar arquivo modificado, pela hash: 

    git checkout + hash do commit

#### Restaurar ao Arquivo principal main: 

    git checkout main

#### Reversão da alteração no Commit:

**Head (Referência principal)**: É uma referência especial que aponta para o commit mais recente em um ramo específico.
Ele representa a posição atual em que você está no histórico do repositório. Basicamente, o "HEAD" indica a versão do código-fonte que você está visualizando ou trabalhando

    git revert HEAD + hash do commit

### *Branch*

**Ação**                        |**Comando** 
---                             |---
Criar Branch                   :| ``` git branch nome-branch                ```
Navegar entre Branch           :| ``` git checkout nome-branch              ```
Criar Branch + acessa-la       :| ``` git checkout -b nome-branch           ```
Criar Branch a partir de outra :| ``` git branch nome-branch nome-branch-2) ```
Deletar Branch                 :| ``` git branch -d nome-branch             ```
Deletar Branch Definitivo      :| ``` git branch -D nome-branch             ```
Listar Branch                  :| ``` git branch                            ```
Listar Branch+ commit          :| ``` git branch -v                         ```


Observação: Mudando nome de Main para Master  = ``` git branch -M "Master"  ```


### *Merge*

*Unificação de informações das Branch*

Para realizar o merge, é necessário estar no branch que deverá receber as alterações. O merge pode automático ou manual. O merge automático será feito em arquivos textos que não sofreram alterações nas mesmas linhas, já o merge manual será feito em arquivos textos que sofreram alterações nas mesmas linhas.

*Fazer Merge* :

    git merge nome-branch

**Ação**                      |**Comando** 
---                           |---
Listar branch Unificadas     :| ``` git branch --merged    ```
Listar branch não Unificadas :| ``` git branch --no-merged ```

## GITHUB

O Github é um site onde podemos armazenar nossos repositórios Git.

#### *Setar usuário:*

    git config --global user.name "Nome do Github"

#### *Setar Email:*

    git config --global user.email nome@email.com.br

#### *Setar Editor de texto:*

    git config --global core.editor nome-editor

#### *Ações no Terminal para Github:*

**Ação**                       |**Comando** 
---                            |---
Enviar repositório            :| ``` git push -u origin main     ```
Enviar arquivo                :| ``` git push                    ```
Puxar um arquivo              :| ``` git pull                    ```
Enviar Branch                 :| ``` git push origin nome-branch ```
Clonar repositorio localmente :| ``` git clone link-repositorio  ```

- **Git push:**  Comando usado no Git para enviar as alterações locais do seu repositório para um repositório remoto. Ele sincroniza o seu repositório local com o repositório remoto,enviando os commits e ramificações que foram feitos.

- **Git pull:**  É o oposto do git push, o push envia as alterações para o Github (ou outro serviço) já o git pull irá baixar esses alterações (caso tenham sido feitas em outro computador ou por outro usuário), ambos atualizam o repositório, com o push atualizamos o repositório remoto com o pull o repositório local.