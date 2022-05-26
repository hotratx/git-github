# Tags
Tags são labels que podemos colocar nos commits pra ter um tipo de identificação 
por versão. Se não identificarmos o commit da tag, será aplicado no corrente 
commit ou no HEAD.

Criando uma tag com nome e refência de branch

    git tag unstable develop
    git tag stable master

quando criamos uma tag, ela ficará associada com o último commit da branch.

Há dois tipos de tag:

* *lightweight*: que podemos dar um nome.
    
    git tag mytag

podemos listar apenas por tags

    git tab --list

* *annotated*: podemos ter informação extra associada a tag.
    
    git tag -a v1.0 -m "Release 1.0 (Alpha)" 763fg873

flag -a: anotamos o nome da tag
flag -m: prove uma menssagem associada a tag.
por fim definimos a que commit queremos associar está tag.

para ver o comentário da tag usamos o comando show seguido do nome da tag.

    git show v1.0

Enviar as tags para o github, por default elas não são enviadas. Podemos enviar
apenas tag especificas 

    git push origin stable

onde stable é o nome de uma tag. Para enviar todas as tags de uma vez

    git push --tags


#### Deletar tag

    git fetch -p

a flag -p irá fazer o fetch de todas as referências correntes. Para deletar
uma tag localmente:

    git tag -d <name-tag>

Podemos deletar tag remota diretamente do terminal. Primeiramente deletarmos 
a tag localmente. Após 

    git push origin :<name-tag-deletada>

assim será deletado a tag no repo remoto.


#### Update tags

Com o tempo podemos querer ir atualizando nossas tags, por exemplo a tag unstable
queremos adicionar mais commmits. Para mudar o commit associado a tag usamos a
flag -f

    git tag -f <name-tag-update> novoIDcommit

Para enviar as mudanças de tag para o remote usamos:

    git push origin <name-tag>

ao fazer isso o github irá informar que já temos uma tag com esse nome e a operação 
será rejeitada.

Teriamos que primeiro deletar a tag remota e depois fazer o update, ou podemos
fazer a força.

    git push --force origin <name-tag>

Assim será forçado a fazer o update.


