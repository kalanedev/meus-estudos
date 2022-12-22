api.md
# APIs
APIs são conjuntos de padrões que fazem parte de uma interface e permitem a criação de plataformas de maneira mais simples e prática para desenvolvedores. A partir dela podemos criar softwares, aplicativos, programas e plataformas.
## O que é? 
Application Programming Interface, que na sua tradução é interface de programação de aplicação, é um conjunto de normas que possibilita a comunicação entre plataformas através de uma série de padrões e protocolos.
A partir delas os desenvolvedores podem comunicar algo que eles fizeram (softwares e aplicativos) com outra coisa que já existe seguindo um padrão, sem ter a necessidade de criar uma interface nova do zero. Por exemplo: se você cria um aplicativo para armazenamento de fotos, pode usar a API do SO para ter acesso à camera ao invés de criar toda uma interface para a câmera para poder fazer isso.
Quando você for criar uma plataforma, você já vai ter o código com as funções que o programa deve executar seguindo um padrão. Ela também é boa por questões de segurança porque podem bloquear acesso e permissões a dados tanto em relação a software quanto hardware.
## Exemplos de utilização
Podemos observar o uso das APIs quando realizamos compras online, já que a plataforma utilizada para pagamentos — em que colocamos as informações de cartões de crédito — deve ser integrada à operadora do cartão, que pode ou não autorizar a compra; podemos ver no facebook, que faz a conexão com o instagram; no whatsapp, que acessa os contatos para poder usá-los também, e assim por diante.
## Servidor e cliente
Podemos dividir em servidor e cliente, sendo a API que faz a solicitação o servidor e a que a autoriza(ou não) cliente.
Quando você abre alguma aplicativo que pede para que você permita o uso da câmera, por exemplo, você está definindo qual será a resposta do cliente para a solicitação do servidor.
Podemos dividir as APIs em quatro, cada uma depende de quando foi criada e qual a finalidade de cada uma delas, sendo que a diferença entre elas é a maneira que vai retornar aquilo que foi solicitado.
### APIs SOAP
Essas APIs usam o Simple Object Access Protocol (Protocolo de Acesso a Objetos Simples). Cliente e servidor trocam mensagens usando XML. Esta é uma API menos flexível que era mais popular no passado e perdeu sua popularidade devido ao fato de ser mais pesado, mais complexo e retornar apenas em XML.
### APIs RPC
Essas APIs são conhecidas como Remote Procedure Calls (Chamadas de Procedimento Remoto). O cliente conclui uma função (ou um procedimento) no servidor e o servidor envia a saída de volta ao cliente.
### APIs WebSocket
É outro desenvolvimento de API da Web moderno que usa objetos JSON para transmitir dados. Uma API WebSocket oferece suporte à comunicação bidirecional entre aplicativos cliente e o servidor. O servidor pode enviar mensagens de retorno de chamada a clientes conectados, tornando-o mais eficiente que a API REST.

-- desenho e explicação melhor do conceito
### APIs Rest
REST significa transferência representacional de estado e é o que define um conjunto de funções (GET, PUT, DELETE, etc) que os clientes podem usar para acessar dados. Nese tipo a comunicação clente e servidor é usando HTTP.
Sua principal característica é a ausência de estado, ou seja, os dados do cliente não são salvos entre as solicitações.
Essas são as APIs mais populares e flexíveis encontradas na Web atualmente. O cliente envia solicitações ao servidor como dados. O servidor usa essa entrada do cliente para iniciar funções internas e retorna os dados de saída ao cliente.
### Principais benefícios da API Rest
* integração - você não precisa ficar reescrevendo funções uma por uma, pois a API permite que você já tenha um padrão feito para seguir e conseguir conectar a sistemas de software existentes;
* inovação - apenas com alterações no nível da API todo o sistema pode ser mudado caso haja alguma nova aplicação, não há a necessidade de reescrever todo o código.
* expansão - elas dão a oportunidade das empresas fornecerem aquilo que os clientes querem em diferentes plataformas. Você pode criar diversas coisas de uma maneira muito mais simples apenas utilizando APIs já existentes (gratuitas ou não).
* facilidade de manutenção - cada sistema é obrigado a fazer alterações internas para a API não ser afetada, então qualquer alteração futura de código feita por uma parte não afetará a outra parte.
### API Web
É uma interface de processamento de aplicações de um servidor web e um navegador web. Todos os serviços da Web são APIs, mas nem todas as APIs são serviços da Web. A API REST é um tipo especial de API Web que usa o estilo de arquitetura padrão explicado acima.
### Integrações de API
São componentes de software que atualizam automaticamente os dados entre cliente e servidor, como quando você viaja para um lugar co outro fuso horário e a hora muda automaticamente.
### Tipos de API
As APIs são classificadas pela arquitetura (que foi falado anteriormente) e uso, agora explicarei os escopos de uso:
* APIs privadas - são internas a empresa, usada apenas para conectar dados e sistemas dentro da empresa;
* APIs públicas - são abertas e podem ser usadas por qualquer pessoa, vale lembrar também que pode ter um custo e autorização.
* APIs de parceiros - apenas desenvolvedores externos podem acessá-las, pode ser usada na parceria entre empresas, por exemplo.
* APIs compostas -  é a combinação de duas ou mais APIs para fazer algo que seja m ais complexo.
### Endpoint de API
São os pontos de contato finais no sistema de comunicação da API, que inclui todos os locais onde as informações são enviadas e recebidas. Eles são fundamentais para empresa por dois motivos:
* segurança - os endpoints tornam o sistema vulnerável, então é necessário que sempre esteja monitorando a API para garantir que não há algum tipo de uso indevido;
* performance - os endpoints (principalmente de alto tráfego) podem causar gargalos e afetar a performance do sistema.
### Como proteger uma API rest

MÉTODOS DE AUTENTICAÇÃO (separado)

Todas devem ser protegidas através de monitoramento e autenticação adequados. A duas principais maneiras incluem:
* tokens de autorização - autorizam os usuários a fazer a chamada de API. Eles verificam quem é o usuário e as permissões que ele tem.
* chaves de API - verificam o programa ou aplicação que fez a chamada de API. Identifica a aplicação e garante que tenha acesso aquela API específica.
### Como criar uma API
Além de cuidade e esforço são necessárias cinco etapas para fazer o design de uma API de qualidade: 
* planejar - pensar nos diferentes casos de uso e garantir que vai estar de acordo com os padrões atuais;
* criar - prototipar usando código boilerplate (seções de código que são repetidas em vários lugares cmo pouca ou nenhuma variação) e depois personalizar de acordo com as especificações internas;
* testar - é o mesmo que o teste de software e deve ser feito para evitar bugs e defeitos, e as ferramentas podem ser usadas para testar a resistência da API contra ataques cibernéticos;
* documentar - apesar de serem autoexplicativas, funciona como um guia para melhorar o uso, e as bem documentadas fornecem várias funções e casos de uso;
* comercializar - existem marketplaces de API para devs comprar e vender outras APIs, ao catalogar você pode ganhar dinheiro com ela.
### Teste de API
A forma de fazer é parecida com os testes de software, focando em validar as respostas do servidor. Para isso é necessário:
* fazer solicitações a endpoints para testar a performance;
* escrever testes de unidade para verificar a lógica e correção funcional;
* testar a segurança simulando ataques.

### Como escrever a documentação da API
Isso faz parte do processo de gerenciamento de API, sendo que pode ser gerada automaticamente usando algumas ferramentas ou escritas manualmente. Algumas práticas recomendadas são:
* escrever explicações simples e fáceis de entender em inglês, sendo que os gerados automaticamente podem exigir edição;
* usar exemplos de código para explicar o uso;
* sempre estar atualizada e ser precisa;
* ser escrita de maneira que iniciantes compreendam;
* ter todos os problemas que ela pode solucionar para os usuários;
### Como usar uma API
Para implementar:
* possuir uma chave de API criando uma conta verificada com o provedor da mesma;
* configurar um cliente de API HTTP, essa ferramente permite que tenha solicitações de maneira mais fácil usando as chaves recebidas;
* se não tiver um cliente, estruturar a solicitação por conta própria no seu navegador consultando a documentação;
* quando se familiarizar com a nova sintaxe dela, pode começar a usar no código.
### Novas APIs
Podemos encontrar novas APIs em marketplaces e diretórios de APIs. Os marketplaces como dito anteriormente são plataformas em que as pessoas catalogam suas APIs, e os diretórios são repositórios controlados e regulamentados pelo dono do diretório. Designers experientes podem avaliar e testar antes de subir.
### Gateway de API
É uma ferramenta de gerenciamento de APIs para clientes empresariais que usam muitos serviços de backend. Eles costumam lidar com tarefas comuns (autenticação de usuários, estatísticas e gerenciamento de taxas).
### GraphQL
É uma linguagem de consulta desenvolvida especificamente para APIs, fornecendo aos clientes exatamente o que eles pedem, nada a mais nem a menos. Foi projetada para tornar APIs rápidas, flexíveis e amigáveis ao desenvolvedor.
Como alternativa ao REST, ele oferece ao frontend a capacidade de consultar vários bancos de dados, microsserviçoes e APIs com apenas um endpoint de GraphQL. Ao usar apenas ele para criar a API fica mais fácil de desenvolver aplicações, o que torna mais rápido.

A criptografia é o que assegura os dados das APIs, se for feita de forma errada deixa os dados vulneráveis e algum hacker, por exemplo, pode acessá-los. Imagina se são dados de banco? Deus é mais.

------------------------------------------------------------------------------------------------

# Testes de API com Postman
O postman é cosiderado um framework simples de usar e melhor para o manuseio de toda a equipe, já que ele faz a automação e verificação dos testes.
Para a realização de testes é necessário que primeiro validemos os campos que tem que ser preenchidos na request da API e depois os campos obrigatórios, para a partir disso preenchermos de forma correta e errada, simulando os cenários positivo e negativos.
O retorno da aplicação sempre deve seguir o que está escrito na documentação.
## Conteúdos da documentação
Tudo que será listado abaixo está especificado na documentação, aqui vamos mostrar como ficam ao ser exibidos na tela.
EX.de response body (campos e formatos esperados para a validação):

{
    "id":0,
    "category": {
        "id":0,
        "name": "string"
    },
    "name": "doggie",
    "photoUrls": [
        "string"
    ],
    "tags": [
        {
            "id": 0,
            "name": "string"
        }
    ],
    "status: "available"
}

EX. de response headers:

access-control-allow-headers: Content-Type,api_key,Authorization
access-control-allow-methods: HET, POST, DELETE, PUT
access-control-allow-origin: *
content-type: application/json
date: wed, 24 feb 2021 12:48:56 GMT
server: Jetty(9.2.9.v29150224)

No status code tem a descrição do response body e se foi uma operação com sucesso ou não.
Devemos verificar se o tempo de resposta está bom de acordo com o que era esperado e o formato do arquivo, no caso de ter mais de um tipo, devemos validar nos que estão na documentação.
## Testes funcionais
Nos testes funcionais veremos se a API faz o que deveria ser feito, devemos testar de forma que mostre que está funcionando como deveria. Muitas vezes precisamos de mais de uma requisição, e tá tudo bem. Vale lembrar também que isso serve tanto para o cenário positivo quanto para os cenários negativos.
Precisamos validar se ela consulta, cadastra, altera, apaga como deveria e se os dados trafegados por ela são válidos.
