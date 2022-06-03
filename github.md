# Git Remote
Podemos ligar um repositório local a um remoto.

O comando mostra as conexões do repositório local

    git remote -v

Para adicionar um repositório local ao github
    
    git remote add origin https://github.com/ksjdlfj

o subcomando add tem dois argumentos o primeiro o origin (será a representação 
do endereço é um alias pode ser qualquer nome, se não colocarmos nada por padrão 
será `origin`), o segundo o endereço do repositório remoto. Por convenção 
definimos o nome origin como repositório principal.

Para verificarmos qual o repositório que estamos conectados usamos:

    git remote -v

#### Push to remote
Para enviar pro repositório remoto usamos:

    git push -u origin master --tags

* -u: indica que vamos colocar o nome do diretório remoto aqui origin. 
Na primeira vez, depois não será mais necessário?
* em seguida dizemos qual branch vamos enviar
* se quisermos enviar as tags, adicionamos a flag --tags.

#### Git Remote add
Quando queremos adicionar mais de um repositório, no caso de termos feito um fork
queremos sincronizar tanto com o nosso fork quanto com as novas mudanças feitas
no projeto principal.

    git remote add upstream <endereço do repositório>

Usamos upstream para nos referirmos ao repositório principal e origin para 
o nosso fork.

### Sincronizar o diretório local com o do github

Comando pull é na verdade a combinação do comando fetch e o merge. Pull é 
destrutivo, pode perder conteúdo que está no repositório local com o merge
com o repositório remoto.

O comando fetch não é destrutivo. Uma boa pratica é sempre fazer o pull ou fetch
antes de fazer um push. Ou seja, ficar em conformidade com as alterações que
estão no repositório remoto, para então enviar novas modificações.

Usamos o pull para sincronizar o local com o remoto.

    git pull --all

irá atualizar (tracking) todos os branchs locais.

### Alterações no nome do repositório pelo github
Ao fazer está alteração temos que atualizar os repositórios remotos.
Para ver os repositórios atuais.

    git remote -v 

Atualizando os repositórios:

    git remote set-url origin git@github.com:hotratx/novoname.git

para ver o resultado

    git remote show origin


Para sincronizar branch com o repositório remoto

    -u igual a ==set-upstream-to

    git branch --set-upstream-to=origin/master

após sincronizar aparece se temos modificações para enviar e para receber.

#### Após deletar branch mortas
Após deletar branch do repositório remoto e do local ainda fica a referência
em 
    
    git branch -a

para limpar as branchs mortas aplicamos o prune

    git fetch -p

#### Nova branch no repo remoto
Para ver se existe uma nova branch no repo remoto temos que dar um 

    git fetch

ápos basta olhas nas branchs

    git branch -a

## Ver as configurações do git

Vai abrir pelo vim, aqui podemos definir os programas que devem ser usados em
casa tipo de comando.

    git config --list
    git config --global -e

## Deletando branch remoto pelo local
Para deletar um branch remoto utilizamos

    git push origin :<name-branch-será-deletado>

## origin/master
Ao inspecionar os commits temos o ponteiro `origin/master` que aponta para o 
repositório remoto.

>`origin` representa o endereço do repositório remoto.

#### Branchs Remotas
Para ver as branchs remotas temos a flag `-r`

    git branch -r

Para ver todas as branchs de uma vez usamos a flag `-a`

    git branch -a

#### Atualizar repo remoto
Para atualizar o repositório remoto precismos `empurrar` os commits, para isso 
usamos o comando `push`

    git push origin master:master

* `origin` é o repositório remoto.
* o primeiro `master` é de qual branch partem os commits, neste caso é a 
master local. O segundo `master` é para qual branch remota queremos empurrar 
esse commits, se não especificarmos ele vai procurar para a branch com mesmo 
nome da local.

Podemos trackear a branch para não precisar ficar especificando a cada push. Para 
isso temos a flag `-u`

    git push -u origin master

a partir de agora não precisamos mais especificar pois o git já trackeou que a 
branch master deve empurar para a branch master do repositório.

### Adicionar nova branch no repositório remoto
O git vai procurar uma branch chamada `teste` no remoto, caso não encontre ele
irá criar uma nova branch chamada `teste`.

    git push origin teste

Podemos trackear a branch `teste` do repositório local com o remoto com a 
flag `-u`

    git push -u origin teste

### Enviar commits de uma branch para outra branch
Será criada uma nova branch no repositório remoto com o nome de `bug` e tera os 
commits da branch master local.

    git push origin master:bug

### Branchs remotas que não estão no repo local
Podemos ver as branchs remotas como comando

    git branch -r 

Podemos usar o seguinte comando

    git branch bug origin/bug
    
assim a branch `bug` já vai ficar trackeada com a `bug` remota.
