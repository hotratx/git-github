## Remover arquivos
Se o arquivo for `untracted` basta deletar o arquivo da pasta, já que o git ainda
não está cuidando dele.

Para manter documentado utilizamos a ferramenta rm do próprio git

    git rm <file>

dessa forma mantemos registrados todas as mundanças feitas no projeto, a 
remoção do arquivo já vai para a `staged area`.

Cado queiramos voltar uma modificação em um arquivo que já foi comitado uma vez
usamos os comandos

    git checkout -- arquivo
    git restore arquivo

para desfazer as alterações que ainda não foram pro `staged`. Quando enviamos 
a modificação para a `staged area`. Podemos retirar a modificação
da `staged area` e aplicar o método anterior.     

### Alteração de nome de arquivos
O git possui um comando para fazer alterações de nomes de arquivos.

    git mv home.html index.html

o proprio git fará a alteração no nome do arquivo e está mudança aparecerá
na `staged area`.


## Reset de commits
Quando queremos voltar commits, temos 3 tipos:

* soft reset (--soft)
Retorna o HEAD para o commit indicado. Preserva o staging area e working directory.
Ou seja, todas as alterações que fizemos do commit que voltamos até o último
permanecem nessas areas para que possamos fazer avaliações do que deu errado.

    git reset --soft IDcommit

* default (--mixed)
O HEAD vai para o commit apontado e todoas as modificações que foram feitas deste
commit em diante aparecem como modificação. Mantém modificações no stage area.

    git reset --mixed IDcommit

* hard reset (--hard)
O HEAD vai para o commit apontado e apaga todas as modificações que foram feitas
deste commit em diante. Mas não perdemos tudo, o hist mantém todos os commits
que estão a frente.

    git reset --hard IDcommit

### Revert
Quando queremos voltar um commit X mas manter o seu historico usamos o `revert`.
O `revert` vai gerar um novo commit removendo as alterações do commit X.
Assim o commit será mantido no historico o commit X e acima teremos o novo commit
feito pelo `revert` no qual ele desfaz todas as alterações do commit X.


## Para enviar pro stage area apenas arquivos deletados
Vai subir para a stage area apenas arquivos que foram deletados.

    git add -u

## Editar o último commit
Para editar titulo de último commit ou adicionar alterações usaos o `--amend`

    git commit --amend

WARNING: ele muda o id do commit logo deve ser usado apenas localmente.

## Adicionar um commit especifico
Caso queira pegar apenas um commit de um branch sem pegar todas as mudanças. 
Queremos pegar apenas a `cereja do bolo`

    git cherry-pick hash


## Commitar em partes
Irá abrir um menu para decidir se queremos ou não adicionar tais pedaços.

    git add -p

## Juntar vários commits em commits menores
Rebase também serve para trabalhar com o historico. 
Vamos juntos os últimos dois commits:

    git rebase -i HEAD~2

-i: interativo

vai arbir o texto com as informações disponíveis. Vamos usar o `squash` para 
juntos os dois commits.

### --fixup
Vamos corrigir o último commit.

    git commit --fixup hash

Será criado um novo commit e depois quando usarmos a opção `--autosquash` ele 
já vai identificar que queremos fazer um fixup.

### Podemos ter conflitos com a branch remota
Para lidar com isso podemos usar o rebase
    
    git pull origin master --rebase

# Verificar 

    git checkout .
