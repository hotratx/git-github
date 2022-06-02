### Ver as confifurações globais do git 
Mostra as configurações globais a flag -l é para listar.

    git config --global -l
    git config --global --list

#### Para alterar o editor padrão 

    git config --global core.editor "nvim"


### Configurando alias

    git config --global alias.hist "log --oneline --graph --decorate --all"

A flag `--all` vai mostrar todos os commit de todas as branchs.

### Configure user and email

    git config --global user.name "Sam Smith"
    git config --global user.email sam@example.com

###  Alterar config local
Caso precise alterar os dados de usuário em algum diretório alteramos a flag 
`global` para `local`.

    git config --local user.name "Outro usuario"
    git config --local user.email outo_email@example.com

# Para mudar o diretório origin
Alteramos o origin para o notes

    git remote set-url origin git@github.com:hotratx/notes.git

