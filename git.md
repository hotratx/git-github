# Git e Github

- [Comandos](#comandos)
  - [Desfazer mudanças](#desfazer-mudanças)
  - [Diff](#diff)
- [HEAD](#head)



[⬆️ Back to top](#tabela-conteúdo)<br>

## Comandos

## Não track arquivos e pastas
Para o git ignorar arquivos basta especificar adicionar no arquivo
.gitignore. Dentro deste arquivo colocamos o nome do arquivo com sua extensão e as pastas que não queremos que o git mapeie.


## Adicionar ao stage aerea todos tipos de modificações
Ao renomear, criar, deletar arquivos podemos usar apenas um
comando para subir todas as mundanças pro stage area

    git add -A

## Ver o historico
Podemos ver o historico de commit em arquivos especificos

    git hist -- <file>

### Log
Para ver todos os commits utilizamos o log

    git log


# Comando Stash
Quando temos alterações no git status podemos armazenadas no stash, limpando o
working diretory.

    git stash

Para ver se temos algo no stash
    
    git stash list

Para devolver as modificações no working directory

    git stash pop


## Git reflog
Ao contrário do git log que mostra os commits IDs, o reflog mostra todas
as ações que foram feitas no projeto. Podemos usar esse registro para
retornar a algum ponto mesmo depois de um reset. Basta aplicar o reset no 
commit desejado.


## Conflitos
Para ver as diferenças entre Rebase e Merge veja este artigo <https://www.treinaweb.com.br/blog/git-merge-e-git-rebase-quando-usa-los/>

Definindo vimdiff como padrão do mergetool

    git config --global merge.tool vimdiff

ou alterando diretamente pelo arquivo

    git config --global -e


Para resolver os conflitos usamos

    git mergetool

vai abrir o vimdiff.
Após salvar as alterações verificamos se temos algum arquivo .orig podemos deletar
com:

    rm *.orig

e dar um

    git rebase --continue

Usamos a flag -A para marcar a resolução de conflito

    git add -A
    git rebase --continue

Se fizermos algumas modificações que não interessem:
    
    git stash
    git pull

# vimdiff
Comandos para selecionar remote, base, local

    :diffget 1,2,3

# Comparando com github


