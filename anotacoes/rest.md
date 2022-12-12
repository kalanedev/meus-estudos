## O que é uma API?
APIs são conjuntos de padrões que fazem parte de uma interface e permitem a criação de plataformas de maneira mais simples e prática para desenvolvedores. É um conjunto de normas que possibilita a comunicação entre plataformas através de uma série de padrões e protocolos.   
A partir delas os desenvolvedores podem comunicar algo que eles fizeram (softwares e aplicativos) com outra coisa que já existe seguindo um padrão, sem ter a necessidade de criar uma interface nova do zero. Por exemplo: se você cria um aplicativo para armazenamento de fotos, pode usar a API do SO para ter acesso à camera ao inves de criar toda uma interface para a câmera para poder fazer isso.   
Quando você for criar uma plataforma, você já vai ter o código com as funções que o programa deve executar seguindo um padrão. Ela também é boa por questões de segurança porque podem bloquear acesso e permissões a dados tanto em relação a software quanto hardware.

--------------

* API application - se preocupa em desenvolver apenas a parte da interface: website, native apps e social integrations (facebook, twitter...). Todos vão se comunicar com a API. Desenvolvemos o Rest API apenas, e ele irá se comunicar com os demais.

* Resource (recursos) - são coisas que podem ser manipuladas através de um ID. Ex.: recurso - usuário      id:site.com/user. Vale ressaltar que a nomeação do recurso é sempre um substantivo, nunca verbo

* URI - identificador uniforme de recurso. É a cadeia de caracteres que vai identificar unicamente na internet o recurso. No ex. anterior seria site.com/user. Porque pode ter "user" em vários sites, mas ESSE é unicamente do site.com     

* URL - localizador padrão de recursos. Ela traz o protocolo (HTTP), a URI e o recurso. 

* URN - um tipo de URI que usa o URN Scheme e tem como objetivo a identificação única do recurso, de forma persistente e independente da localização. (não utilizado)

* IRI - identificador de recursos internacionalizado (generalização da URL). Contém caracteres especiais pré definidos.

## API Rest
REST significa transferência representacional de estado e é o que define um conjunto de funções (GET, PULL, DELETE, etc) que os clientes podem usar para acessar dados. Nesse tipo a comunicação clente e servidor é usando HTTP.   
Sua principal característica é a ausência de estado, ou seja, os dados do cliente não são salvos entre as solicitações.   
Essas são as APIs mais populares e flexíveis encontradas na Web atualmente. O cliente envia solicitações ao servidor como dados. O servidor usa essa entrada do cliente para iniciar funções internas e retorna os dados de saída ao cliente.


## Constraints
São os conjuntos das melhores práticas, sendo elas:
* cliente-servidor: tem como principal característica separar as responsabilidades de diferentes partes de um sistema. É a divisão front-back.
* stateless: cada requisição não deve ter ligação com requisições anteriores ou futuras, deve contar apenas as informações necessárias para fazer o que foi pedido.
* cache: para uma melhor performance, um sistema REST deve permitir que suas respostas sejam passíveis de cache
* interface uniforme: devemos deixar tudo no padrão, seguindo: recursos-> mensagens autodescritivas-> hypermedia

![diagrama top](/.github/img/rest-1.png) 

* sistema em camadas: podemos colocar algo no meio do caminho  e aquilo será transparente ao cliente. Balanceia a carga de requisições.
* código sob demanda (opcional): tem como ideia aumentar a flexibilidade dos clientes. Ex.: um códgo JS que só é baixado quando determinada página é carregada. É opcional pois reduz a visibilidade do que está sendo baixado.

RESTFUL - API que segue os princípios REST.

Representações - o formato em que será devolvida a informação solicitada pelo cliente.
Mais utilizadas: JSON(chave e valor), XML(tag).

## Rest vs Soap
As APIS Sopar usam o Simple Object Access Protocol (Protocolo de Acesso a Objetos Simples). Cliente e servidor trocam mensagens usando XML. Esta é uma API menos flexível que era mais popular no passado. 
Temos como principais diferenças entre os dois tipos:
| REST | SOAP |
|---|---|
| é um modelo arquitetural | é um protocolo |
| requisição HTTP simples | usa SOAP envelopado no HTTP para fazer chamadas RPC |
| suporta vários formatos (JSON, XML, YAML) | só suporta XML |

## CURL
É uma ferramenta de comando para pegar ou enviar arquivos utilizando sintaxe URL. Tem um conjunto de opções que permitem você moificar qualquer coisa na requisição que será enviada.

### Atalhos do CURL:
* -H -> atalho para Header. Essa opção permite adicionar ou substituir campos do cabeçalho HTTP. Ex.: -H "Content-Type: application/json"
* -d -> atalho para data. Usamos quando queremos enviar dados para o servidor. Ex.: -d '{"name":"Luluzinha top"}'
* -i -> ou -include -> para o CURL mostrar, além do corpo, o cabeçalho da mensagem
* -I ou -head -> diz ao CURL para fazer uma requisição tipo Head; traz somente o cabeçalho
* -X ou -request -> especifica qual o verbo HTTP queremos usar. O padrão é GET, mas podemos usar POST, PUT, PATCH, DELETE.
* curl --help -> mostrar os comandos que você pode usar

O que o CURL mostra como resposta de uma requisição HTTP pode ser dividido em 4 partes:
* start line: linha de início, é obrigatória. Pode ser dividida em duas partes: request-line e status-line. A request-line indica a versão do HTTP que foi usada e logo em seguida vem a status line com a resposta, como no exemplo abaixo: 

![exemplo de requisição](/.github/img/rest-2.png)

* header fields: cabeçalho de campos, pode ter 0 ou mais. Representam os metadados da requisição e resposta HTTP. Contém informações sobre como a transferência de dados deve ser manipulada, como por exemplo:   
  * content-type - informa como você vai receber a informação enviada  
  * content-lenght - informa o tamanho do corpo da mensagem em octetos
  * x-powered-by - header fiels não oficiais começam com X, mas devemos evitar ao máximo e optar pelos oficiais.                 Caso seja realmente necessário, podemos não começar com X.

* empty line: linha em branco, é obrigatória. Delimita o fim dos header fields e o início do corpo da menasgem.

* message-body: corpo da mensagem, é opcional. Contém os dados que foram enviados do servidos em resposta à requisição feita. Vale ressaltar que o curl -v também faz uma requisição e tem o resultado mais verboso.

OBS.: apesar de cada requisição ter uma resposta diferente, toda terão a start line e a empty line

## Métodos para criar uma API Rest
Para isso podemos utilizar 9 métodos, e cada um deles tem uma semântica de operações:
* GET - para pegar dados de um recurso. NÃO MODIFICA OS DADOS
* POST - usado para CRIAR um item de um recurso. Ex.: já tem um user, mas vou usá-lo para criar outro além do já existente
* PUT - atualizar
* DELETE - apagar determinado recurso
* PATCH - faz modificações parciais nos recursos (muda valores específicos ao invés de enviar todos os dados novamente).

![métodos para criar uma API Restful](/.github/img/rest-3.png)

* OPTIONS:  é a forma do cliente perguntar ao servidor quais os requisitos para determinado recurso. Ex.: quais métodos, qual URL...
* ACCESS-CONTROL-ALLOW-METHODS: mostra quais os métodos que podem ser usados. É importante que você exemplifique os métodos para facilitar quando as pessoas forem utilizar
* TRACE: ele volta a requisição recebida para o cliente ver se houve alguma mudança ou adição feita por servidores intermediários
* CONNECT: converte a requisição para um túnel TCP/IP transparente, usualmente para facilitar a comunicação criptografada com SSL através de um proxy HTTP não criptografado.


## Safe Methods
São métodos que não fazem nenhum efeito em nenhum dos lados (cliente/servidor).   
Dá pra implementar algo para quando o safe method for chamado, como atualizar o contador de um usuário, mas o cliente não pode ser responsável por essa alteração. Temos como safe methods GET e HEAD que trazem somente as informações.

## Metódos Idempotentes
São métodos que você pode rodar várias vezes e não vai modificar o resultado após a primeira. São eles: GET, HEAD, PUT, DELETE, OPTIONS e TRACE.

## Modelo de maturidade - Richardson
Leonard Richardson fez uma analise em centenas de API's diferentes. E dividiu em quatro categorias para identificar o nível de maturidade da API com base no quanto eles são compatíveis com REST. Esse modelo é chamado de modelo de maturidade de Richardson. Os níveis são:
* 0 -> POX
* 1 -> Recursos
* 2 -> Verbos HTTP
* 3 -> HATEOAS   

### POX
| verbo HTTP | URI | Ação |
|---|---|---|
| GET | /buscarCliente | visualizar |
| POST | /salvarCliente | criar |
| POST | /alterarCliente | alterar |
| GET / POST| /deletarCliente | remover |

### HATEOAS 
Tem como elemento principal uma representação hypermedia, que permite um documento descrever seu estado atual e quais os relacionamentos com outros futuros estados.

### Resumo
* 0 -> você não sabe usar o HTTP corretamente 
* 1 -> agora você tem recursos
* 2 -> agora você sabe usar os verbos HTTP corretamente
* 3 -> agora você usa controles de hypermedia

## Ferramentas além do CURL
* HTTPie: tem highlights, faz a documentação correta, sintaxe mais simples...
* Postman: é cosiderado um framework simples de usar e melhor para o manuseio de toda a equipe, já que ele faz a automação e verificação dos testes.   
Para a realização de testes é necessário que primeiro validemos os campos que tem que ser preenchidos na request da API e depois os campos obrigatórios, para a partir disso preenchermos de forma correta e errada, simulando os cenários positivo e negativos.   
O retorno da aplicação sempre deve seguir o que está escrito na documentação.

## Media Type
É uma string que define o formato do dado e como deve ser lido pela máquina. Isso permite que o PC diferencie JSON e XML, por exemplo(application/json e application/xml).

* antes da barra é o tipo e depois o subtipo. Tambem dá para especificar alguns parâmetros adicionais como o charset=UTF-8.

### Tipos registrados de alto nível
* application                                      
* audio                                            
* example                                          
* image                                            
* message
* model
* multipart
* text
* video

## Outras informações importantes
* Para informar o mediatype usamos o header field Accept na hora da requisição, ele também pode encadear outros tipos em uma mesma requisição, basta separar por vírgula.   
* O parâmetro q define quality factor, que informa a ordem preferida do retorno. Deve estar no parâmetro entre 0 e 1, sendo 1 o de maior prioridade. Ex.: dou valor 0.5 para um XML e 1 para JSON, o que quer dizer que aceito os dois mas tenho preferência pelo JSON.   
* Media type e mime type são a mesma coisa.
* A diferença entre content-type e accept é que num POST(por exemplo) o formato dos dados deve ser indicado no content-type e o accept deve informar o tipo de retorno do servidor.

## Gerindo Erros
Quando fazemos requisições Restful, recebmos como retorno um possível erro por falha no formato da requisição ou causas internas referentes ao servidor. A mensagem opde não ser clara, então o intuito da gerência de erros é informar ao requisitante de uma forma explicativa.   
Vale lembrar que normalmente só retorna o status code.

### Classes dos HTTP Status Code
* Informacional: começa com 1 e a maioria não é usado atualmente
* Success: começa com 2 e indica sucesso no servidor/cliente
* Redirection: começa com 3 e indica que o cliente deve fazer uma ação adicional antes da requisição estar completa
* Cliente error: começa com 4 e indica erro na requisição do cliente
* Server error: começa com 5 e a requisição foi válida mas o server não processou com sucesso

No site [Lista e definição dos Status Code](httpstatuses.com) lista e define os Status Code.

## Versionamento
Isso faz com que você crie uma API que suporte as mudanças pode ser com:
* subdomínio -> api.example.com/users
* URL -> example.com/v1/users
* HTTP Header customizado -> X-API-Version:1
* URL com parâmetro -> example.com/users?v=1
* Accept Header com Media Type customizado -> Accept: application/vnd.myapi.v2+json
* Accept Header com opção de versão -> application/vnd.myapi+json;version=2.0

A mais usada ultimamente é através de URL, e tem como pontos positivos: fácil implementação, permite compartilhar facil e evita erros de programadores novatos.


CACHING -> reduz o custo de rodar aplicações 
* qualquer valor que é difícil e computacionalmente custoso de se obter deve ser cacheado 
* não devemos cachear o que muda com frequência (real time)

CACHE INVALIDATION -> processo feito para saber se o cache está desatualizado

PONTOS CHAVE SOBRE CACHING
* pode economizar muito tempo (pq??)
* gasta menos com servidores, pois quando dimínuimos o tempo as aplicações demoram menos para rodar
* permite que uma aplicação cresça sem "atrapalhar"
* alguns dados não real time e é muito difícil tentar cacheá-los 
* os demais variam no tempo conforme o dado é atualizado

OBJETIVO DO CACHING
* eliminar o envio de requisições o máximo possível
* caso precise fazer mesmo assim, reduz os dados de resposta
 -> usando um mecanismo de expiração chamado cache-control
 -> usando um mecanismo de validação ETag ou Last-Modified

 Prevenir Requisições - para fazer uma requisição HTTP de um jeito mais rápido podemos não enviá-la inteira, o Header cache-control que define isso. Ex.:
 cache-control: max-age = 3600
(desenho explicando que max-age especifica o tempo para ser cacheado em SEGUNDOS)
 também pode ser feito por roteadores, proxy etc

private/public - define quem pode fazer o cache, sendo pruvate apenas o browser e public qualquer um, inclusive intermediários como por exemplo roteadores

no cache - pode ser cacheada mas não reusada sem checar o server, e pode ser combinada com um Etag
no store - não deve ser armazenada no browser sem intermediários

Outras diretivas que podem ser usadas encontramos em: [diretivas que podem ser usadas](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/cache-control)

ETag -> Entity tag, assegura um token de validação identificando uma versão específica de uma resposta
o token pode ter letras e números como por exemplo um HASH (explicar)
na maior parte das APIs web é raramente possível fazer caching (pq), então usamos ETag para ganhar tempo e reduzir custo

timestamp -> é a data da última atualização, podemos usar para verificar se está desatualizado
Para isso é melhor usar a header Last-Modified associado a header If-Modified-Since seguindo a mesma lógica da ETag

CACHE COM DIFERENTES TIPOS DE REPRESENTAÇÃO
* podemos fazer requisições para vários tipos de representação usando o Header Accept
* mesmo que tenhamos várias representações diferentes o browser fica confuso de qual resposta fazer cache devido a ser o mesmo verbo HTTP e URI
* para resolver temos o header Vary que permite indicar outros itens para composição do cache. Ele pode informar mais de uma chave


-----------------
### wip

