# Principais tags HTML

ii gente! Eu trouxe algumas das tags mais importantes para se saber em HTML, espero que facilite a compreensão de quem está começando agora e seja tão útil quanto para mim.

Vou falar por partes, começando pela estrutura: em HTML nós abrimos o <!DOCTYPE HTML> e a tag <html> para mostrar que é o que usaremos. 
É dividido em duas partes: head e body, sendo dentro do head informações gerais (metadados) sobre o documento, incluindo seu título e links para scripts e folhas de estilos, e no body todo o conteúdo da página. 
Vale lembrar também que no head nós temos a tag title, que vai definir o nome da sua página, como no exemplo abaixo:


## HTML semântico

Usando html semântico para marcar suas páginas, você pode criar páginas que são mais acessíveis, tanto para as pessoas com deficiência, bem como aos motores de busca. Marcação semântica ajuda os motores de busca determinar qual é a relevância do conteúdo de uma página, e facilita para a pessoa que for ler seu código depois, seja outra pessoa ou até mesmo você no futuro.

### Tags semânticas

Começamos com bold, representado pela tag b, que significa negrito, e strong.

Os dois deixarão o texto em <b>negrito</b>, mas semânticamente falando, <strong>strong</strong> seria o correto, pois ele mostra para quem for ler aquele código que é importante destacar aquela parte.

Assim como o italic, que é representado pela tag i, e emphasis, representado pela tag em.

Os dois deixarão o texto em itálico, sendo semânticamente correto usar a tag em, para mostrar que aquele texto precisou ser destacado.

### Underline

Representada pela tag u, ela vai fazer com que o texto dentro dela tenha uma linha embaixo, como <u>aqui</u>, por exemplo.
        
<!-- é usado para fazer comentários, neles você pode colocar anotações que achar necessárias para quem for ler seu código depois, para fechar é só usar -->

### Listas ordenadas

As listas ordenadas são representadas pela tag ol, que quer dizer ordered list, como o próprio nome já diz, e dentro delas temos o li, que significa listed item, onde você vai colocar os itens que você quer que a sua lista tenha.

Essas listas podem ser em ordem de números, letras, números romanos sejam eles maiúsculos ou minúsculos, é só definir o type dentro da tag, como no exemplo abaixo:

        

### Listas não-ordenadas

As listas não-ordenadas são representadas pela tag ul, que quer dizer unordered list, tendo dentro dela também a tag li para colocar os itens da sua lista.

Essa lista também tem uma variedade que é definida pelo type dentro da tag. Pode ser em círculos (circle), quadrados (square) ou um disco preenchido (disc), assim como no exemplo abaixo:

       

### Imagem e link

Para colocar imagens, usamos a tag img, que vem com alt e scr, sendo um para o link da imagem e outra para descrever a imagem caso ela não carregue, por exemplo. 

        

Para o exemplo do link, vou deixar o meu perfil no twitter, inclusive segue lá :)

### Table

A tag table é representada pelo próprio nome, e serve para a criação de tabelas, podendo ter dentro um border ou width, por exemplo.

Dentro da tag table nós temos algumas outras, as quais vou listar e explicar abaixo:

      

Nós temos também o <td colspan="">, que é a extensão da coluna, ele faz com que uma coluna ocupe 2 espaços, por exemplo; e o <td rowspan="">, que mostra para o browser que você tem duas linhas com a mesma definição, como se fossem duas linhas na segunda coluna que pertencem a mesma linha na primeira.

### Formulários

Para criar formulários em HTML nós usamos a tag form, podendo ser form action="" para que seja possível fazer alterações na página de alguma linguagem de programação de sua preferência.

Dentro do formulário nós podemos colocar opções para que a pessoa marque, vou listá-las abaixo:
      
input type="" para definir o tipo e o nome, nesse caso o tipo seria texto e o nome será utilizado mais adiante para poder recuperar seus dados, caso o type do input seja password, ele vai continuar sendo uma entrada de dados, e a senha não aparecerá.
input type="submit" value="" p type submit entende que ao pressionar o botão, aquelas informações serão processadas, mas elas aparecerão na URL então é importante depois usar uma linguagem de programação para corrigir isso.
input type="radio" name="" ele vai dar opções para a pessoa marcar, ao invés de escrever, limitando as opções, podem ter vários inputs mas é necessário que tenham o mesmo name para que não dê para marcar mais de um, mas o value diferente.
input type="checkbox" name="" ele também dá opções a serem marcadas, podendo ser marcada mais de uma opção.
select name="" permite que o usuário escolha apenas uma opção baseada em uma lista, indicado para quando a listagem é grande.option para definir as opções que irão no select, dentro dele pode colocar um value com o conteúdo para poder recuperar os dados pelo name com uma linguagem de programação.
textarea é uma caixa de texto onde a pessoa poderá escrever, por exemplo, observações.

### Caracteres Especiais

Temos dificuldade, por exemplo, em escrever uma tag que deve aparecer em algum site, porque a partir do momento que você a escreve, ela é considerada uma tag e não apenas um texto, então para fazer isso temos as Entidades HTML, onde vai ensinar como usar esses tipos de dados que normalmente não apareceriam. Há uma lista deles, um exemplo é o que eu usei para colocar < e > nas tags.
