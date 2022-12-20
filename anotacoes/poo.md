# Programação orientada à objetos

Uma das características da POO é fazer com que o progemador pense nas coisas de formas distintas, dividindo elas em obetos e aplicando propriedades e métodos.


## Características

A POO trabalha utilizando classes, dá vida ao objeto. É nela que criamos as funções através dos métodos dizendo o que o objeto deverá fazer, e as especificidades pelos atributos (cor, nome...). A classe NÃO é o objeto, é utilizada para CONSTRUÍ-LO.
O objeto é uma abstração de software que pode ser algo representado, que é formado por conjunto de propriedades(variáveis) e procedimentos(métodos) onde as variáveis possuem um tipo que define os possiveis valores. Métodos são rotinas que quando executadas realizam algumas tarefas, como alterar o conteúdo de uma variável do objeto. A classe é a ABSTRAÇÃO do objeto. Ao programarmos um objeto, definir suas características e funcionalidades, estamos programando uma classe.

## Principais recursos aplicados na POO:

### Abstração 
É um dos pontos mais importantes dentro de qualquer linguagem orientada a ojetos. VOcê precisa imaginar o que o objeto irá realizar dentro do nosso sistema, e pra isso devemos levar em consideração 3 pontos:
+ identidade - deve ser única dentro do sistema;
+ características - chamamos de propriedades;
+ ações - chamamos de métodos e podem ser extremamente variáveis.

### Encapsulamento 
A limitação imposta a atributos em uma classe, restringindo o acesso aos métodos da classe através de limitadores. Os limitadores mais usados são:
+ public - a classe só é vista pelas outras classes se estiverem no mesmo pacote;
+ protected - o acesso se restringe a apenas a própria classe e suas "filhas";
+ private - o acesso só é permitido pela própria classe

### Herança 
Nos permite definir uma nova classe com base em uma que já existe. A classe filha herda todas as variáveis e métodos da classe mãe. Ela também permite que a filha inclua ou sobreponha novas variáveis e métodos da mãe. Esse recurso permite criar uma hierarquia de classes e facilita a construção de novos objetos sem precisar reescrever.

## Outros conceitos importantes
Orientação a objetos é um tipo de modelo de análise do código onde você segue padrẽs para que ele fique mais organizado e descritivo, baseando-se em objetos.
+  **Objeto** - você pode criar vários dentro de uma classe a partir de algo que já existe.
+ **Classe** - molde usado para criar outros objetos.
	- `public` - acessa dentro e fora da classe
	- `protected` - apenas dentro da classe e suas filhas
	- `private` - só dentro da classe
Quando você trabalha com atributos privados, você está falando de:
+ `get` - acessar um atributo privado de uma classe
+ `set` - setar um valor em um atributo; é uma atribuição ao atributo da classe

## Os quatro pilares da POO
- **encapsulamento** - agrupamos o que faz sentido ficar junto para organizar o código. Ao encapsular o código será refatorado e teremos entçao dentro da classe as variáveis (que passrão a ser o que chamamos de propriedades) e as funções (que passarão a ser métodos). Isso é o que dá origem ao nosso objeto.
- **herança** - é uma boa prática fazer "cópias" dentro do código. Ao invés de você fazer, por exemplo, várias possibilidades de formas de pagamento dentro de uma classe, você pode criar um filho da classe principal. Essa classe filho vai herdar as características da classe pai.
- **abstração** - significa esconder os detalhes de uma implementação. Para isso usamos o private.
- **polimorfismo** - um objeto assume diversas formas diferentes. Para não precisar reescrever, por exemplo, várias vezes a mesma regra.

