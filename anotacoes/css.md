# Folha de estilo CSS

### CSS - cascale style sheet, que significa folha de estilo em cascata. Usando o CSS podemos formatar o site, colocando cor, organizando, etc.
- Modos de incorporar estilos:
    + Inline style - formatação direto no elemento;
    + Internal style sheet - coloca o estilo direto dentro do código;
    + External style sheet - coloca as formatações em um arquivo externo (recomendado e mais utilizado);
- Básico de CSS

## Modos de incorporar estilos

### Inline style
Você aplica o estilo na mesma linha ou na própria tag
- Exemplo: 
```css
<p style="color: black"></p>
```
Nós estilizamos o nosso parágrafo, deixando ele preto com uma estilização dentro da própria tag.

### Internal style sheet
Dentro do `<head></head>` nós colocamos informações tanto para formatação quanto para execução de códigos para o nosso body, lembrando que eles não vão aparecer diretamente para o usuário.
Nós escrevemos `<style type="text/css"></style>`, pois é o que colocaremos aqui dentro, um estilo em CSS, usando seletores. Tudo dentro da tag style!
- O seletor tem a seguinte estrutura:
```css
<style>
p {
    color: black;
}
</style>
```
- O seletor vem antes das chaves, dentro dele vai a propriedade (`color`) e logo em seguida o valor (`black`), com a declaração no final (`;`). Nesse caso formatamos usando a tag p, podendo colocar qualquer outra como seletor, e você pode formatar mais de uma tag ou colocar mais de uma propriedade dentro da mesma.

### External style sheet
Para isso você cria um arquivo css e dentro do style você coloca a tag `<link rel="stylesheet" href="styles.css"></link>`, sendo rel para definir o relacionamento que esses arquivos terão (exemplo: stylesheet), o type para o tipo de conteúdo (text/css) e href para colocar o caminho da nossa folha de estilo (nome do arquivo e da pasta caso não esteja na mesma). Assim você consegue colocar apenas isso em todas as páginas e mesmo que sejam 30 as alterações serão feitas em todas.
- Exemplo:
```css
<link rel="stylesheet" href="css/styles.css"></link>
```


## Básico

### Classes e IDs
ID é um identificador. Imagine um ônibus, o ID são as poltronas, dentro do site o ID é para identificar apenas UM, sendo a classe para usar vários, como chamar todos os passageiros idosos, tendo mais de um.

Para utilizar uma classe o seletor terá um . e o nome da classe logo em seguida, depois colocamos dentro das tags que queremos aplicar a formatação class="nomedaclass".
Para usar um ID o seletor terá # e o nome dele logo em seguida, colocando dentro da tag que queremos aplicar a formatação id="nomedoid", lembrando que teremos apenas UM por página.

### Div e Span
Com a div você cria divisoes no seu site. Se você tem colunas no seu site, por exemplo, cada uma delas seria uma divisão, podendo usar a div e aplicando formatações logo em seguida. Lembrando que você pode ter quantas divs você achar necessário. A div é um elemento tipo block, então ela ocupa 100% da largura da tela.
Span é um elemento do tipo inline, ele agrupa os elementos linha a linha, ele coloca os conteúdos um na frente do outro, já a div coloca um emabaixo do outro por ser um elemento tipo block.

### Bordas
Para definir a borda usamos `border: 1px solid red;`, sendo o primeiro valor a expessura, o segundo o estilo e o terceiro a cor., mas vale ressaltar que tem vários tipos de borda e vários estilos.
`/* para fazer comentários em CSS */`

### Fontes e cores
As cores que tem por padrão podem ser escritas em inglês, mas para criar cores podemos usar alguns sites como html-color-codes, onde você escolhe a cor e ele vai dar o codigo que corresponde aquela cor para que você possa usá-la.
O tamanho da fonte é definido por font-size, o tipo de fonte é definido por font-family.

### Tamanho de textos
+ `px` - tamanho fixo em pixels
+ `%` - tamanho relativo em porcentagem
+ `em` - tamanho relativo ao container pai

### Estilos de textos
Para definir o peso da fonte usamos font-weight, podendo ficar normal, e ir aumentando para que ele fique em negrito com números de 100 até 900. No `font-style` podemos colocar italic para deixar em italico, por exemplo. Com `text-decoration` nós podemos usar vários tipos de "decoração", como por exemplo: underline, overline, line-through.

### Cor e imagem de fundo
- **backgrond-color**: muda a cor do fundo, seja do body, do h1 ou de qualquer outra tag.
- **background-image:** coloca uma imagem de fundo, e usamos **background-repeat**: `no-repeat` para que a imagem de fundo não se repita várias vezes tanto da horizontal quanto na vertical, e `repeat-x` ou `repeat-y` para que se repita no eixo x (horizontal) e eixo y (vertical).
- **background-attachment**: fixed faz com que a imagem fique fixe como plano de fundo, mesmo que você role a página para baixo ela continua lá, e scroll não a deixa fixa, fazendo com que conforme você desça a página a imagem suba.
- **background-position** define a posição da imagem, podendo estar no centro (center), esquerda (left), direita (right), no topo (top) e na parte inferior (bottom).
- Podemos usar mais de um de uma vez, como por exemplo o `background: blue url("") no repeat fixed center;` para conseguir aplicar tudo o que aprendemos anteriormente de uma só vez.

### Box model (modelo de caixa)
As tags se comportam como caixa, por isso damos esse nome. Cada caixa tem uma borda, onde podemos aplicar o padding(espaçamento para dentro da caixa), o margin.

### Elementos flutuantes
Ajudam na criação dos layounts.
É representado por float, que pode ser à direita(right), esquerda(left) ou none, isso é o que vai definir a posição da "caixa" selecionada. Para 'limpar' o fluxo de elementos flutuantes usamos a propriedade clear, que pode ser `left`, `right`, `both` e `none` para que ele entenda que quer que "limpe" o excesso de flutuantes e reorganizar.

### Elementos inline, block e inline block
Essas divisões fazem com que os elementos tenham comportamento diferente. Podemos alterar o comportamento padrão usando display.
+ **block**
    + Ocupa todo o espaço em tela e fica um abaixo do outro.
+ **inline**
    + O elemento inline fica um à frente do outro e a largura é de acordo com o conteúdo.
+ **inline block**
    + O inline block tem a largura definida e fica um abaixo do outro.

### Posicionamentos (static, relative, absolute e fixed)
Se usarmos auto no margin, por exemplo, o elemento ficará centralizado mesmo que você aumente ou diminua a tela. O posicionamento padrão é estático (`static`), mas podemos alterar, deixando por exemplo relativa:
- **Relativa** - precisa de propriedades de deslocamento (`top`, `right`, `bottom` e `left`);
- **Absoluto** - o elemento que definimos com essa posição sai do fluxo normal e todos os outros elementos agem como se ele não estivesse ali;
- **Fixo** -  ele fica fixo naquele lugar, se você rolar a página por exemplo ele não vai rolar junto. é alinhado baseado na tela;

    z-index - usamos para organizar as posiçoes de dois conteúdos que estão, por exemplo, um sobre o outro.

### Formatar links
Quando usamos a: link estamos formatando o padrão de um link, formatando por exemplo um link ainda não visitado;
- **a:visited** -> para formatar um link que já foi visitado;
    + Exemplo: 
    ```css 
    a:visited {
        color: #000;
    }
    ```

- **a:hover** -> para mudar o link quando você passar o mouse em cima, tenha visitado ou não;
    + Exemplo: 
    ```css 
    a:hover {
        color: #f11;
    }
    ```

- **a:active** -> para modificar links quando você clica e segura, é importante manter essa ordem para a formatação;
    + Exemplo: 
    ```css 
    a:active {
        color: #c3d;
    }
    ```