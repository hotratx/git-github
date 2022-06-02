## Conflitos
Quando temos conflitos entre branchs e queremos aplicar um merge ou um rebase.

### Resolvendo conflitos
O git irá pedir para resolvermos os conflitos. Podemos resolver e continuar ou
abortar o merge.

#### Resolvendo
Podemos resolver os conflitos
assim o arquivo em questão irá aparecer como `modified` basta adicionar no 
`stage area` e commitar.

#### Abortando
Podemos abortar o merge com o comando 

    git merge --abort

## Conflito do rebase 
Quando temos um conflito no merge (merge cria um commit de rebase), o rebase não 
possui um commit de rebase, logo ele para no meio do processo e pede para 
que resolvemos manualmente o conflito e depois podemos continuar com o rebase 
ou abortar.

Depois de resolver o conflito damos continuidade ao rebase

    git rebase --continue

caso preferimos abortar o rebase

    git rebase --abort 

existe outra opção que é `skip` (pular) o commit.

    git rebase --skip
