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
