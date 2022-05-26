# Branchs
Para criar um novo branch e ativa-ló usamos a flag -b

    git branch -b featurea

#### Para alternar entre os branchs

    git checkout name_branch

#### Fazer o merge entre branchs
Primeiro temos que ir para o branch que queremos manter, e aplicamos o merge

    git merge featureb

O comando merge não vai deletar o branch featureb, então temos que fazer isso:

    git branch -d featureb

#### Merge conflict
Quando ocorre um conflito no merge será apresentado o problema e as opções para
resolver ser for possível.

#### branch -a
A flag -a, mostra todas as nossas branchs.


#### Mudar o branch padrão

    git config --global init.defaultBranch <name>
