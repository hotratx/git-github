### Ver as confifurações globais do git 
Mostra as configurações globais a flag -l é para listar.

    git config --global -l
    git config --global --list

#### Para alterar o editor padrão 

    git config --global core.editor "nvim"


### Configurando alias

    git config --global alias.hist "log --oneline --graph --decorate --all"

### Configure user and email

    git config --global user.name "Sam Smith"
    git config --global user.email sam@example.com

# Para mudar o diretório origin
Alteramos o origin para o notes

    git remote set-url origin git@github.com:hotratx/notes.git

