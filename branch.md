# Branchs
Para criar um novo branch e ativa-ló usamos a flag -b

    git branch -b featurea

#### Para alternar entre os branchs

    git checkout name_branch

#### Deletar uma Branch 
Para deletar uma branch temos que ir para outra branch. 

    git branch -d teste

Caso não aplicamos um merge ou rebase e queremos perder os commits que foram 
feitos na branc teste precisamos usar a flag -D com d maiúsculo.

    git branch -D teste

#### branch -a
A flag -a, mostra todas as nossas branchs.


#### Mudar o branch padrão

    git config --global init.defaultBranch <name>
