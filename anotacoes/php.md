

# Basicão de PHP

## Sintaxe

Para entendermos como é escrito a linguagem PHP, primeiro precisamos entender suas regras gramaticais:

- **Variaveis de Abertura/Fechamento**: indica pro interpretador que a partir daquela tag, você está escrevendo ou finalizando o dialeto PHP.
- **Ponto e Virgula**: finaliza uma estrutura de comando (ou uma linha) que não seja estrutura de condição ou repetição.

tags do php

<?php - é a tag de abertura, ela serve para identificar que a linguagem que será usada é o PHP
?> - para fechar o bloco de código
 *Se for apenas um script em PHP não é necessário fechar a tag :)

 Funções

 echo - exibe uma ou mais strings, pode (e deve) ser usada para conferir se o código funciona ou não
 var_dump - mostra as informações da varável selecionada

 Comentários

 Não aparecem quando o código está sendo lido e serve para que você documente tudo que achar necessário ser relembrado depois (por você ou por quem acessar o código)
 
 comentarios de linha única: representados por "//" no PHP 
 comentários de múltipla linha: inicia com "/**", a cada linha você coloca um novo asterisco e para fechar usa "*/"

 TIpos de dados no php
 Evitam que sua aplicação não dê certo por um erro "comum", como números inteiros e flutuantes, dentro deles temos:

 boleanos - o mais simples, dá um  valor de verdade e é dividido em TRUE e FALSE. identificado por "var_dump(true/false), se é o true ou false é você quem decide :)

 inteiros - ao avisar que o número é inteiro ele considera os que antes não enquadravam, como números negativos e decimais. identificado por "int()"

 números flutuantes - é identificado por "\n"

 strings - um conjunto de caracteres, independente de quais, é representada por aspas simples ou duplas

Para quebrar a linha nas strings usa-se "\n" ao final. Exemplo 

arrays - Imagina o jogo da cobrinha, aquele lá que conforme ela come uma maçã ela cresce de tamanho.É como se cada parte dela fosse parte de um vetor, dentro dele você pode colocar strings, variáveis... qualquer coisa, até mesmo outros vetores. Vale lembrar que tudo dentro do vetor é separado por vírgulas e tem posições diferentes, começando pelo 0, pode-se usar a posição para mostrar o que você quiser dentro do vetor. pode ser feito com "array()" ou "[]"

variáveis - é um espaço de memória que guarda um valor. Uma coisa sensacional no PHP é que você não precisa tipar a variável, o que facilita caso você queira mudar depois. As variáveis são definidas por "$" e é importante que o cifrão venha seguido de uma letra. Para juntar duas variáveis ou strings usa-se "." entre os dois.

Operadores Aritméticos
Vou explicar separadamente, mas vamos aprender agora os seguintes: adição, subtração, multiplicação, divisão e módulo (resto da divisão).

adição - é represando por "+" e realiza a soma de duas variáveis

subtração - é representado por "-" e realiza a subtração de duas ou mais variáveis

multiplicação - é representado por "*" e realiza a multiplicação de duas ou mais variáveia

divisão - representado por "/" e divide duas ou mais variáveis

módulos - representado por "%" ele realiza a divisão e mostra o resto dela, o que sobra

exponencial - representado por "**" ele dá o resultado de uma variável elevada a outra (a partir do PHP 5.6)

Assim como nos problemas de matemática que vemos na escola, no PHP podemos fazer várias contas ao mesmo tempo, podendo usar por exemplo 3 operadores em uma só linha.

Operadores bitwise
Eles operam em um ou mais padrões de bits, ou números binários no nível de seus bits individuais. Vale lembrar que bits são a menor unidade de informação na computação e são representados por 0 e 1. Esses operadores são usados para manipular valores para comprações e cálculos. Temos vários opperadores, por exemplo:

Operador E (&)- retorna 1 se os bits comparados forem iguais a 1, se forem diferentes ele retorna 0

Operador OU (|) - retorna 1 se UM DOS bits comparados for igual a 1, se não, ele retorna 0

Operador OU exclusivo (^) - retorna 1 se ambos os bits comparados forem diferentes, se não, retorna 0

Operador Não (~) - ele inverte os bits, então o que era 0 vira 1 e o que era 1 vira 0

Operador deslocar a esquerda (<<) - cada < é um passo, cada passo multiplica por dois, então se for $number << 4 ele vai multiplicar $number por 2, 4 vezes.

Operador deslocar a direita (>>) - a diferença é que os passos são para a direita e ao invés de multiplicar ele vai dividir

Operadores de atribuição
Atribuição é um jeito de guardar um valor e identificar

atribuição (=) - ele dá o valor de algo, por exemplo, se $number = 2, quer dizer que a variável tem esse valor, é valor que foi dado a ela

Vou mostrar alguns exemplos de atribuição abreviada, onde você não precisa criar outra variável para que a conta seja feita.

Você vai colocar += na próxima linha com a mesma variável que você quer que execute a SOMA. 

~~~php
<?php

$number = 4;
$number += 4;

echo $number;

//o resultado será 8 
~~~

para subtração será usado -=

~~~php
<?php

$number = 4;
$number -= 4;

echo $number;

//o resultado será 0
~~~

para a multiplicação *=

~~~php
<?php

$number = 4;
$number *= 4;

echo $number;

//o resultado será 16
~~~

para a divisão temos /=

~~~php
<?php

$number = 4;
$number /= 4;

echo $number;

//o resultado será 1
~~~ 

Por fim, para o módulo usará %=

~~~php
<?php

$number = 4;
$number %= 4;

echo $number;

//o resultado será 0
~~~

Operador de incremento e decremento (++ e --)
É importante ressaltar que a ordem do operador é crucial, então se você colocar antes ele vai considerar a variável ANTES da avaliação, e depois da variável, DEPOIS da avaliação.













Comparação de valores
Antes de mostrar as opções de comparação de valores, é importante que você saiba que:
* true significa verdadeiro e false significa falso;
* true é a mesma coisa que 1, logo;
* false é a mesma coisa que 0;
* para quebrar linhas usamos PHP_EOL ao final delas;

Comparadores
igualdade - representado por == ele mostra true se os valores apresentados forem iguais e false se eles forem diferentes

diferença - representado por != ele testa se os valores são diferentes, se forem é true e se forem iguais é false

idêntico - representado por === ele pode testar se os valores é do mesmo TIPO (se os dois são string, por exemplo)

não idêntico - representado por !== ele mostra se o valor é identico, no caso para verificar isso o PHP usa o TIPO do valor

maior/menor - para esse comparador temos o menor (<), maior (>), menor ou igual (<=) e maior ou igual (>=). eles indicam que tal valor é maior, menor, maior opu igual ou menor ou igual a outro que você definir. se realmente for, true, do contrário, false.

Concatenação de strings
Para isso juntaremos as string, mas há também formas abreviadas, as quais mostrarei logo em seguida.

apenas concatenar - representada por "." ela junta duas strings

concatenar abreviadamente - representada por ".=" ela une a variável que está em linhas diferentes, por exemplo:

concatenar variáveis - como o nome já diz, ela une duas variáveis diferentes, como:

Operadores de arrays
Podemos fazer operações com os arrays, e aqui vou explicar melhor sobre elas:

uniao - representado por +, serve para unir o VALOR de um ou mais arrays

igualdade - representado por == ele 













