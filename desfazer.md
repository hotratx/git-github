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


