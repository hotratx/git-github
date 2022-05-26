# Comandos Básicos

- [Status](#status)
- [Show](#show)
- [Ls-files](#ls-files)
- [Commit](#commit)
- [diff](#diff)


### Status
Mostra o status do projeto, se possui arquivos modificados, untracked (git 
ainda não mantém este arquivo), arquivos deletados. 

    git status

### Add 
Para adicionar arquivos novos ou mudanças na área `staged`.

    git add file 
    git add . 

Quando usamos `add .` será adiciona na staged área todos os arquivos.

### Show
Mostra o diff do último commit, se usar uma flag -n irá mostrar o diff do 
n-ésimo commit.

    git show
    git show -3

[⬆️ Back to top](#tabela-conteúdo)<br>

### Ls-files
Ver os arquivos que estão sendo monitorados (tracked)

    git ls-files

[⬆️ Back to top](#tabela-conteúdo)<br>

### Commit
Quanto temos um arquivo modificado precisamos add no stage area 
para depois comitar, podemos utilizar a flag -a para entrar no 
vim e commitar sem precisar add primeiro.

    git commit -a

Podemos combinar com a flag -m para comitar diretamente no terminal
sem entrar no editor de texto.

    git commit -am "Meu commit"

[⬆️ Back to top](#tabela-conteúdo)<br>


### diff
Usamos para verificar todos os tipos de mudanças entre commits, 
stage area, e até mesmo entre branchs.

    git help diff

O diff entre dois commit

    git diff <commit> <commit>

[⬆️ Back to top](#tabela-conteúdo)<br>

Podemos ver as diferenças entre o estado atual do projeto e um commit passado.
Vai mostar as diferenças em todos os arquivos.

    git diff IDcommit 

Podemos visualizar pelo vim, usando o comando

    git difftool IDcommit

Também é possivel aplicar o comando `diff` entre diferentes branchs.
Precisamos apenas passar os nomes dos branchs:

    git diff branchA branchB
    

