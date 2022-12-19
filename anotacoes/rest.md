# REST4noobs
Explicação básica de APIs REST para iniciantes, mas antes de entrar em REST devemos entender primeiro um pouco sobre APIs.

## O que é uma API?
APIs são conjuntos de padrões que fazem parte de uma interface e permitem a criação de plataformas de maneira mais simples e prática para desenvolvedores. É um conjunto de normas que possibilita a comunicação entre plataformas através de uma série de padrões e protocolos.   
A partir delas os desenvolvedores podem comunicar algo que eles fizeram (softwares e aplicativos) com outra coisa que já existe seguindo um padrão, sem ter a necessidade de criar uma interface nova do zero. Por exemplo: se você cria um aplicativo para armazenamento de fotos, pode usar a API do SO para ter acesso à camera ao inves de criar toda uma interface para a câmera para poder fazer isso.   
Quando você for criar uma plataforma, você já vai ter o código com as funções que o programa deve executar seguindo um padrão. Ela também é boa por questões de segurança porque podem bloquear acesso e permissões a dados tanto em relação a software quanto hardware.

Temos alguns conceitos que são importantes e falaremos mais a frente, como:

* API application - se preocupa em desenvolver apenas a parte da interface: website, native apps e social integrations (facebook, twitter...). Todos vão se comunicar com a API. Desenvolvemos o Rest API apenas, e ele irá se comunicar com os demais;

* Resource (recursos) - são coisas que podem ser manipuladas através de um ID. Ex.: recurso - usuário      id:site.com/user. Vale ressaltar que a nomeação do recurso é sempre um substantivo, nunca verbo;

* URI - identificador uniforme de recurso. É a cadeia de caracteres que vai identificar unicamente na internet o recurso. No ex. anterior seria site.com/user. Porque pode ter "user" em vários sites, mas ESSE é unicamente do site.com;     

* URL - localizador padrão de recursos. Ela traz o protocolo (HTTP), a URI e o recurso; 

* URN - um tipo de URI que usa o URN Scheme e tem como objetivo a identificação única do recurso, de forma persistente e independente da localização (não utilizado);

* IRI - identificador de recursos internacionalizado (generalização da URL). Contém caracteres especiais pré definidos.

## Rest vs Soap 
As APIS SOAP usam o Simple Object Access Protocol (Protocolo de Acesso a Objetos Simples). Cliente e servidor trocam mensagens usando XML. Esta é uma API menos flexível que era mais popular no passado e agora não mais devido ao fato de ser mais pesado, mais complexo e retornar apenas em XML.
Temos como principais diferenças entre os dois tipos:
| REST | SOAP |
|---|---|
| é um modelo arquitetural | é um protocolo |
| requisição HTTP simples | usa SOAP envelopado no HTTP para fazer chamadas RPC |
| suporta vários formatos (JSON, XML, YAML) | só suporta XML |

## API Rest
REST significa transferência representacional de estado e é o que define um conjunto de funções (GET, PULL, DELETE, etc) que os clientes podem usar para acessar dados. Nesse tipo a comunicação clente e servidor é usando HTTP.   
Sua principal característica é a ausência de estado, ou seja, os dados do cliente não são salvos entre as solicitações.   
Essas são as APIs mais populares e flexíveis encontradas na Web atualmente. O cliente envia solicitações ao servidor como dados. O servidor usa essa entrada do cliente para iniciar funções internas e retorna os dados de saída ao cliente.

### Constraints
São os conjuntos das melhores práticas, sendo elas:
* cliente-servidor: tem como principal característica separar as responsabilidades de diferentes partes de um sistema. É a divisão front-back;
* stateless: cada requisição não deve ter ligação com requisições anteriores ou futuras, deve contar apenas as informações necessárias para fazer o que foi pedido;
* cache: para uma melhor performance, um sistema REST deve permitir que suas respostas sejam passíveis de cache;
* interface uniforme: devemos deixar tudo no padrão, seguindo: recursos-> mensagens autodescritivas-> hypermedia.

![diagrama top](/.github/img/rest-1.png) 

* sistema em camadas: podemos colocar algo no meio do caminho  e aquilo será transparente ao cliente. Balanceia a carga de requisições;
* código sob demanda (opcional): tem como ideia aumentar a flexibilidade dos clientes. Ex.: um códgo JS que só é baixado quando determinada página é carregada. É opcional pois reduz a visibilidade do que está sendo baixado;

RESTFUL - API que segue os princípios REST.

Representações - o formato em que será devolvida a informação solicitada pelo cliente.
Mais utilizadas: JSON(chave e valor), XML(tag).

## CURL
É uma ferramenta de comando para pegar ou enviar arquivos utilizando sintaxe URL. Tem um conjunto de opções que permitem você modificar qualquer coisa na requisição que será enviada.

### Atalhos do CURL:
* -H -> atalho para Header. Essa opção permite adicionar ou substituir campos do cabeçalho HTTP. Ex.: -H "Content-Type: application/json";
* -d -> atalho para data. Usamos quando queremos enviar dados para o servidor. Ex.: -d '{"name":"Luluzinha top"}';
* -i -> ou -include -> para o CURL mostrar, além do corpo, o cabeçalho da mensagem;
* -I ou -head -> diz ao CURL para fazer uma requisição tipo Head; traz somente o cabeçalho;
* -X ou -request -> especifica qual o verbo HTTP queremos usar. O padrão é GET, mas podemos usar POST, PUT, PATCH, DELETE;
* curl --help -> mostrar os comandos que você pode usar.

O que o CURL mostra como resposta de uma requisição HTTP pode ser dividido em 4 partes:
* start line: linha de início, é obrigatória. Pode ser dividida em duas partes: request-line e status-line. A request-line indica a versão do HTTP que foi usada e logo em seguida vem a status line com a resposta, como no exemplo abaixo: 

![exemplo de requisição](/.github/img/rest-2.png)

* header fields: cabeçalho de campos, pode ter 0 ou mais. Representam os metadados da requisição e resposta HTTP. Contém informações sobre como a transferência de dados deve ser manipulada, como por exemplo:   
  * content-type - informa como você vai receber a informação enviada;  
  * content-lenght - informa o tamanho do corpo da mensagem em octetos;
  * x-powered-by - header fiels não oficiais começam com X, mas devemos evitar ao máximo e optar pelos oficiais.                 
  Caso seja realmente necessário, podemos não começar com X.

* empty line: linha em branco, é obrigatória. Delimita o fim dos header fields e o início do corpo da mensagem;

* message-body: corpo da mensagem, é opcional. Contém os dados que foram enviados do servidor em resposta à requisição feita. Vale ressaltar que o curl -v também faz uma requisição e tem o resultado mais verboso.

OBS.: apesar de cada requisição ter uma resposta diferente, todas terão a start line e a empty line

## Métodos para criar uma API Rest
Para isso podemos utilizar 9 métodos, e cada um deles tem uma semântica de operações que explicarei em seguida.

### GET
Para pegar dados de um recurso. NÃO MODIFICA OS DADOS;

### POST 
Usado para CRIAR um item de um recurso, ele envia dados para o servidor. Ex.: já tem um user, mas vou usá-lo para criar outro além do já existente.
O tipo do corpo da solicitação é indicado pelo cabeçalho Content-Type.

Geralmente o POST é enviado por meio de um formulário HTML, tendo isso em mente apresentarei em seguida alguns Mime Types, que é o mecanismo para dizer ao cliente a variedade de documentos transmitidos. Os navegadores costumam usar o MIME-type para determinar qual ação usar como padrão para fazer quando um recurso é obtido.

Temos variedades de text, image, audio, video e application.
Há também tipos de Multipart, que indicam uma categoria de documento que são quebrados e muitas vezes com diferentes tipos de mime.

Application
  * application/octet-stream - é o valor padrão para um arquivo binário;
  * application/x-www-form-urlencoded - chaves e valores são codificados de forma separada por &, com = entre chave e valor. Esse tipo não é adequado para uso com dados binários pois caracteres não alfanuméricos em chaves e valores são percent encoded (podemos dizer que não aceita símbolos), então para isso usamos multipart/form-data.   

Multipart  
  * multipart/form-data - para postar arquivos inteiros como parte do envio do formulário;
  * multipart/byteranges - usados juntamente com o 206 Status Code  para enviar apenas um subconjunto de um documento inteiro.

Text  
  * text/plain - é o valor padrão para arquivos de texto;
  * text/css - para arquivos de texto css. Muitas vezes os servidores não reconhecem arquivos com o sufixo .css como arquivos CSS, em vez disso, enviam-nos com o tipo MIME de text/plain ou application/octet-stream: nesses casos, eles não serão reconhecidos como arquivos CSS pela maioria dos navegadores e serão silenciosamente ignorados;
  * text/html - para arquivos de texto HTML. Tipos MIME alternativos para XHTML (como application/xml+html) são em sua maioria inúteis hoje em dia (HTML5 unificou esses formatos).

Image
  * image/gif;
  * image/jpeg; 
  * image/png;
  * image/svg+xml. 

Audio
  * audio/wave, audio/wav, audio/wav, audio/x-pn-wav - arquivo de áudio no formato WAVE;
  * audio/webm - arquivo de áudio no formato de contêiner WebM;
  * video/webm - arquivo de vídeo, possivelmente com áudio, no formato de contêiner WebM;
  * audio/ogg - arquivo de áudio no formato de contêiner OGG;
  * video/ogg - arquivo de vídeo, possivelmente com áudio, no formato de contêiner OGG;
  * application/ogg - arquivo de áudio ou vídeo usando o formato de contêiner OGG.

### PUT
 Cria um novo recurso ou subsititui uma representação do recurso de destino com os novos dados.

### DELETE 
Apagar determinado recurso. Se for aplicado com sucesso há muitos HTTP Status Code possíveis (202 - accepted, 204 - no content, 200 - ok).

### PATCH 
Faz modificações parciais nos recursos (muda valores específicos ao invés de enviar todos os dados novamente).

![métodos para criar uma API Restful](/.github/img/rest-3.png)

* OPTIONS:  é a forma do cliente perguntar ao servidor quais os requisitos para determinado recurso. Ex.: quais métodos, qual URL...
* ACCESS-CONTROL-ALLOW-METHODS: mostra quais os métodos que podem ser usados. É importante que você exemplifique os métodos para facilitar quando as pessoas forem utilizar;
* TRACE: ele volta a requisição recebida para o cliente ver se houve alguma mudança ou adição feita por servidores intermediários;
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
* application;                                      
* audio;                                            
* example;                                          
* image;                                            
* message;
* model;
* multipart;
* text;
* video.

## Outras informações importantes
* Para informar o mediatype usamos o header field Accept na hora da requisição, ele também pode encadear outros tipos em uma mesma requisição, basta separar por vírgula;   
* O parâmetro q define quality factor, que informa a ordem preferida do retorno. Deve estar no parâmetro entre 0 e 1, sendo 1 o de maior prioridade. Ex.: dou valor 0.5 para um XML e 1 para JSON, o que quer dizer que aceito os dois mas tenho preferência pelo JSON;   
* Media type e mime type são a mesma coisa;
* A diferença entre content-type e accept é que num POST(por exemplo) o formato dos dados deve ser indicado no content-type e o accept deve informar o tipo de retorno do servidor.

## Gerindo Erros
Quando fazemos requisições Restful, recebemos como retorno um possível erro por falha no formato da requisição ou causas internas referentes ao servidor. A mensagem pode não ser clara, então o intuito da gerência de erros é informar ao requisitante de uma forma explicativa.   
Vale lembrar que normalmente só retorna o status code.

### Classes dos HTTP Status Code
* Informacional: começa com 1 e a maioria não é usado atualmente;
* Success: começa com 2 e indica sucesso no servidor/cliente;
* Redirection: começa com 3 e indica que o cliente deve fazer uma ação adicional antes da requisição estar completa;
* Cliente error: começa com 4 e indica erro na requisição do cliente;
* Server error: começa com 5 e a requisição foi válida mas o server não processou com sucesso.

No site [Lista e definição dos Status Code](httpstatuses.com) lista e define os Status Code.

## Versionamento
Isso faz com que você crie uma API que suporte as mudanças pode ser com:
* subdomínio -> api.example.com/users;
* URL -> example.com/v1/users;
* HTTP Header customizado -> X-API-Version:1;
* URL com parâmetro -> example.com/users?v=1;
* Accept Header com Media Type customizado -> Accept: application/vnd.myapi.v2+json;
* Accept Header com opção de versão -> application/vnd.myapi+json;version=2.0.

A mais usada ultimamente é através de URL, e tem como pontos positivos: fácil implementação, permite compartilhar de forma mais fácil e evita erros de programadores novatos.

## Caching
Reduz o custo de rodar aplicações. Qualquer valor que é difícil e computacionalmente custoso de se obter deve ser cacheado, mas não devemos cachear o que muda com frequência (real time).

* Cache invalidation é processo feito para saber se o cache está desatualizado.

### Pontos chave sobre Caching
* pode economizar muito tempo, já que a leitura de dados do cache de memória é extremamente rápida; 
* gasta menos com servidores, pois quando dimínuimos o tempo as aplicações demoram menos para rodar;
* permite que uma aplicação cresça sem "atrapalhar";
* alguns dados são real time e é muito difícil tentar cacheá-los, os demais variam no tempo conforme o dado é atualizado.

### Objetivo do Caching
Eliminar o envio de requisições o máximo possível, mas caso precise fazer mesmo assim ele reduz os dados de resposta.
 * usando um mecanismo de validação ETag ou Last-Modified que é melhor explicado nos próximos tópicos;
 * usando um mecanismo de expiração, que especifica o tempo máximo em que um recurso será considerado fresco em segundos (também pode ser feito por roteadores, proxy...). Por exemplo:    
 cache-control: max-age = 3600.    

Ele pode ser private ou public, o que vai definir quem pode fazer o cache. Private permite apenas que o browser faça e public que qualquer um faça, inclusive intermediários como por exemplo roteadores.   

Como exemplo de diretivas cache control vou mostrar duas que se confundem e a diferença entre ambas:    
* no cache - pode ser cacheada mas não reusada sem checar o server, e pode ser combinada com um Etag;
* no store - não deve ser armazenada no browser sem intermediários.    
Outras diretivas que podem ser usadas encontramos em: [diretivas que podem ser usadas](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/cache-control)

Na maior parte das APIs web é raramente possível prevenir requisições usando o cache control pois na API fazemos uma requisição simples e recebemos o retorno do servidor, então usamos ETag para ganhar tempo e reduzir custos.    
* ETag -> Entity tag, assegura um token de validação identificando uma versão específica de uma resposta, sendo que esse token pode ter letras e números como por exemplo um HASH (função Hash é qualquer algoritmo que mapeie dados grandes e de tamanho variável para pequenos dados de tamanho fixo);
* timestamp -> é a data da última atualização. Podemos usar para verificar se está desatualizado, mas para isso é melhor usar a header Last-Modified associado a header If-Modified-Since seguindo a mesma lógica da ETag.

### Cache com diferentes tipos de representação
Mesmo que tenhamos várias representações diferentes o browser fica confuso de qual resposta fazer cache devido a ser o mesmo verbo HTTP e URI, então para resolver temos o header Vary que permite indicar outros itens para composição do cache e ele pode informar mais de uma chave.    
Nós podemos fazer requisições para vários tipos de representação usando o Header Accept

## Identificação x Autenticação x Autorização
Identificação - usa só a API Key para identificar, porém o desenvolvedor pode repassar a API, o que é um problema.     
Autenticação - usa login e senha para confirmar quem é     
Autorização - define o que pode fazer de acordo com as suass permissões

A autenticação pode feita ser através de cookies, que permitem o servidor gravar e manter os estados (stateful), o contrário do que Rest propõe (stateless, uma requisição não depende da outra e torna mais fácil crescer a aplicação).

### Padrão de autenticação HTTP
Como padrão temos basic e através de digest, que são stateless. 
Nesse caso, usuário e senha incluídos em cada requisição, codifica em Base64 para basic e hash MD5 para digest.
* Realm é opcional e indica  proteção de determinado espaço.
Lado negativo: pede login sempre, mas podemos resolver isso com API Key e API Secret Token, que vou explicar abaixo. 

* API KEY - fica sendo transmitida em todas as requisições para identificar aplicação e geralmente é combinada com um email e senha. Para isso é importate que o servidor tenha configurado os certificados SSL para garantir a maior segurança possível.

* TOKEN - manda o usuário e senha pro servidor e recebe um token que é informado em cada requisição através da Header Authorization. Costuma ser escolhida para uso em web API mas não é considerada stateless porque o servidor armazena o token e isso caracteriza o "manter o estado".    
Lado negativo: tem que replicar os dados armazenados na medida que se escala, muitos clientes geram muitos tokens e se cada cliente armazenado tem mais de um token isso dobra facilmente.

### JWT (JSON Web Token)
Como exemplos temos o JWT, que é um padrão aberto especificado pelo RFC 7519, que define uma forma compacta e independente de transmitir informações com segurança entre duas partes utilizando o formato JSON. 
Caso a transmissão de dados seja sigilosa, é possível criptografar.

O JWT funciona da seguinte forma:
Após a autenticação, um token é gerado pelo servidor para identificar o usuário. Toda vez que aquele usuário fizer uma requisição o servidor vai conferir o token. 
Para gerar o token podemos usar, por exemplo, o JWT, que tem a seguinte estrutura:

![estrutura JWT](/.github/img/rest-4.png)

O header é composto por “alg”, que indica o algoritmo de hash utilizado (por exemplo o “HS256”) e por “typ”, que indica o tipo de token (neste caso o “JWT”).

O corpo do token é aberto e pode ser utilizado para adicionar qualquer informação relevante a autenticação e autorização. No entanto, a RFC 7519 define o padrão de algumas claims que podem ser utilizadas de maneira opcional.

“iss” – Issuer (Emissor)
Responsável pela emissão do token.
“sub” – Subject (Sujeito)
A quem pertence o token

“aud” – Audience (Destinatário)
Aplicação que irá utilizar o token

“exp” – Expiration Time (Tempo de expiração)
Data de validade do token

“nbf” – Not Before (Não antes)
Data de início de validade do token, antes dela o token não deve ser aceito

“iat” – Issued At (Emitido em)
Data de emissão do token (em segundos desde a época que já é definida)

“jti” – JWT ID
Identificador único do token

No caso do exemplo abaixo temos apenas sub, name e iat.

A assinatura é composta pelo hash do header, payload e chave secreta utilizada pela aplicação, que pode ser gerada no próprio site. Lembrando que a assinatura de cada token é única.

Como resultado final, teremos:

![token JWT](/.github/img/rest-5.png)





