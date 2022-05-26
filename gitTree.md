## git subtree

#### Adicionar um repo na tree
Dentro do nosso diretório principal vamos add um novo repo
    
    git subtree add --prefix <subrepo-path> <subrepo-remoto> master --squash

- subrepo-path: onde colocaremos o repo
- subrepo-remote: endereço do github por exemplo do repo que queremos pegar
- squash:

#### Atualizar o subrepo
Para atualizar um subrepo usamos o comando

    git subtree pull --prefix <subrepo-path> <subrepo-remoto> master --squash

ex:
    git subtree pull --prefix backend git@github.com:hotratx/back_monitor.git master --squash

#### Enviar modificações de um subrepo
Caso tenha commit no subrepo e queira mandar para o repo do subrepo usamos o 
comando

    git subtree pull --prefix <subrepo-path> <subrepo-remoto> master
