API -> conjunto de padrões de programação para acesso a um aplicativo de software

API application - se preocupa em desenvolver apenas a parte da interface: website, native apps e social integrations (facebook, twitter...). Todos vão se comunicar com a API. Desenvolvemos o Rest API apenas, e ele irá se comunicar com os demais.

Resource (recursos) - são coisas que podem ser manipuladas através de um ID. Ex.: recurso - usuário      id:site.com/user
 * a nomeação do recurso é sempre um substantivo, nunca verbo

URI - identificador uniforme de recurso. É a cadeia de caracteres que vai identificar unicamente na internet o recurso. No ex. anterior seria site.com/user. Porque pode ter "user" em vários sites, mas ESSE é unicamente do site.com     

URL - localizador padrão de recursos. Ela traz o protocolo (HTTP), a URI e o recurso. 

URN - um tipo de URI que usa o URN Scheme e tem como objetivo a identificação única do recurso, de forma persistente e independente da localização. (não utilizado)

IRI - identificador de recursos internacionalizado (generalização da URL). Contém caracteres especiais pré definidos.

REST - transferência de estado representacional


Constraints

* cliente-servidor: tem como principal característica separar as responsabilidades de diferentes partes de um sistema. É a divisão front-back.
* stateless: cada requisição não deve ter ligação com requisições anteriores ou futuras, deve contar apenas as informações necessárias para fazer o que foi pedido.
* cache: para uma melhor performance, um sistema REST deve permitir que suas respostas sejam passíveis de cache
* interface uniforme: devemos deixar tudo no padrão, seguindo: recursos-> mensagens autodescritivas-> hypermedia

![diagrama top](/.github/img/rest-1.png) 

* sistema em camadas: podemos colocar algo no meio do caminho  e aquilo será transparente ao cliente. Balanceia a carga de requisições.
* código sob demanda (opcional): tem como ideia aumentar a flexibilidade dos clientes. Ex.: um códgo JS que só é baixado quando determinada página é carregada. É opcional pois reduz a visibilidade do que está sendo baixado.

REST - conjunto de melhores práticas denominadas constraints. A API que segue os princípios REST é uma API RESTFUL.

Representações - o formato em que será devolvida a informação solicitada pelo cliente.
Mais utilizadas: JSON(chave e valor), XML(tag).

| REST | SOAP |
|---|---|
| é um modelo arquitetural | é um protocolo |
| requisição HTTP simples | usa SOAP envelopado no HTTP para fazer chamadas RPC |
| suporta vários formatos (JSON, XML, YAML) | só suporta XML |

CURL - uma ferramenta de comando para pegar ou enviar arquivos utilizando sintaxe URL. Tem um conjunto de opções que permitem você moificar qualquer coisa na requisição que será enviada.

Algumas opções:
* -H -> atalho para Header. Essa opção permite adicionar ou substituir campos do cabeçalho HTTP. Ex.: -H "Content-Type: application/json"
* -d -> atalho para data. Usamos quando queremos enviar dados para o servidor. Ex.: -d '{"name":"Luluzinha top"}'
* -i -> ou -include -> para o CURL mostrar, além do corpo, o cabeçalho da mensagem
* -I ou -head -> diz ao CURL para fazer uma requisição tipo Head; traz somente o cabeçalho
* -X ou -request -> especifica qual o verbo HTTP queremos usar. O padrão é GET, mas podemos usar POST, PUT, PATCH, DELETE.
* curl --help -> mostrar os comandos que você pode usar

O que o CURL mostra como resposta de uma requisição HTTP pode ser dividido em 4 partes:
* start line: linha de início, é obrigatória. Pode ser dividida em duas partes: request-line e status-line. A request-line indica a versão do HTTP que foi usada e logo em seguida vem a status line com a resposta, como no exemplo abaixo: 

![exemplo de requisição](/.github/img/rest-2.png)

* header fields: cabeçalho de campos, pode ter 0 ou mais. Representam os metadados da requisição e resposta HTTP. Contém informações sobre como a transferência de dados deve ser manipulada. Exemplos abaixo:
  * content-type - informa como você vai receber a informação enviada  
  * content-lenght - informa o tamanho do corpo da mensagem em octetos
  * x-powered-by - header fiels não oficiais começam com X, mas devemos evitar ao máximo e optar pelos oficiais.                 Caso seja realmente necessário, podemos não começar com X.

* empty line: linha em branco, é obrigatória. Delimita o fim dos header fields e o início do corpo da menasgem.

* message-body: corpo da mensagem, é opcional. Contém os dados que foram enviados do servidos em resposta à requisição feita. Vale ressaltar que o curl -v também faz uma requisição e tem o resultado mais verboso.

OBS.: apesar de cada requisição ter uma resposta diferente, toda terão a start line e a empty line


Para criar uma API Restful podemos utilizar 9 métodos e cada um deles tem uma semântica de operações:
    * GET - para pegar dados de um recurso. NÃO MODIFICA OS DADOS
    * POST - usado para CRIAR um item de um recurso. Ex.: já tem um user, mas vou usá-lo para criar outro além do já existente
    * PUT - atualizar
    * DELETE - apagar determinado recurso
    * PATCH - faz modificações parciais nos recursos (muda valores específicos ao invés de enviar todos os dados novamente).

![métodos para criar uma API Restful](/.github/img/rest-3.png)

* OPTIONS:  é a forma do cliente perguntar ao servidor quais os erquisitos para determinado recurso. Ex.: quais métodos, qual URL...
* ACCESS-CONTROL-ALLOW-METHODS: mostra quais os métodos que podem ser usados. É importante que você exemplifique os métodos para facilitar quando as pessoas forem utilizar
* TRACE: ele volta a requisição recebida para o cliente ver se houve alguma mudança ou adição feita por servidores intermediários
* CONNECT: converte a requisição para um túnel TCP/IP transparente, usualmente para facilitar a comunicação criptografada com SSL através de um proxy HTTP não criptografado.


Safe Methods
* são métodos que não fazem nenhum efeito em nenhum dos lados (cliente/servidor).
* dá pra implementar algo para quando o safe method for chamado, como atualizar o contador de um usuário, mas o cliente não pode ser responsável por essa alteração. Temos como safe methods GET e HEAD que trazem somente as informações.

Metódos Idempotentes
São métodos que você pode rodar várias vezes e não vai modificar o resultado após a primeira. São eles: GET, HEAD, PUT, DELETE, OPTIONS e TRACE.

Modelo de 4 níveis de API Restful - Richardson
* 0 -> POX
* 1 -> Recursos
* 2 -> Verbos HTTP
* 3 -> HATEOAS 

Em relação ao POX temos:
| verbo HTTP | URI | Ação |
|---|---|---|
| GET | /buscarCliente | visualizar |
| POST | /salvarCliente | criar |
| POST | /alterarCliente | alterar |
| GET / POST| /deletarCliente | remover |

Já relaciondo ao HATEOAS, vale ressaltar que ele tem como elemento principal uma representação hypermedia, que permite um documento descrever seu estado atual e quais os relacionamentos com outros futuros estados.

Em resumo:
* 0 -> você não sabe usar o HTTP corretamente 
* 1 -> agora você tem recursos
* 2 -> agora você sabe usar os verbos HTTP corretamente
* 3 -> agora você usa controles de hypermedia

Ferramentas além do CURL:
HTTPie -> tem highlights, faz a documentação correta, sintaxe mais simples...
Media Types -> é uma string que define o formato do dado e como deve ser lido pela máquina. Isso permite que o PC diferencie JSON e XML, por exemplo. 
Ex.: application/json e application/xml

* antes da barra é o tipo e depois o subtipo. Tambem dá para especificar alguns parâmetros adicionais como o charset=UTF-8.

Os tipos registrados de alto nível (que vem antes da barra) podem ser:
* application                                      
* audio                                            
* example                                          
* image                                            
* message
* model
* multipart
* text
* video

Para informar o mediatype usamos o header field Accept na hora da requisição.
* ele também pode encadear outros tipos em uma mesma requisição, basta separar por vírgula.

O parâmetro q define quality factor, que informa a ordem preferida do retorno. Deve estar no parâmetro entre 0 e 1, sendo 1 o de maior prioridade. Ex.: dou valor 0.5 para um XML e 1 para JSON, o que quer dizer que aceito os dois mas tenho preferência pelo JSON.

* Media type e mime type são a mesma coisa.

A diferença entre content-type e accept é num POST o formato dos dados deve ser indicado no content-type e o accept deve informar o tipo de retorno do servidor.