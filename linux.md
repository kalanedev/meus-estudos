Fala galera, tudo certo? Trouxe pra vocês alguns dos principais comandos do Linux daquele jeitinho bem simples pra você ver que é bem mais fácil do que parece. Espero que ajude ☺️

### Comandos mais usados

* ls - listar o que tem no diretório.
Ele mostra todos os diretórios existentes para que você possa usá-los.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fsv1eoy7ruwbkklk7044.gif)

* mkdir - make directory. 
O próprio nome já diz: ele cria um diretório, aqui eu criei o diretório "exemplo":

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mpjnzu3wgbckjqapkqad.gif)

* cd - serve para navegar pelos diretórios. Aqui eu entrei no diretório "exemplo", então na próxima linha ele mostra "~/exemplo".


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/oy5do6w5yskxo566wen1.gif)

* touch - criar arquivos.
Aqui fiz o arquivo "ex2", então quando uso o "ls" ele mostra que foi criado.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5x7k2d4qxwp9iteur85n.gif)

* cat - pega o conteúdo de um arquivo e exibe, nesse caso o conteúdo do arquivo "ex2" criado anteriormente.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wrggnqz3k727ohbqlbwp.gif)

* cp -r - copiar. Nesse exemplo eu copiei os diretórios "exemplo e "exemplo2".

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/27eb5qe0qr89126e1tg6.gif)

* mv - mover ou renomear. Movi o exemplo2 para dentro do exemplo3, então o exemplo2 não aparece junto com os outros diretórios mais.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/grs90xym35iictpsiqda.gif)

* rm - remover. Removi o arquivo "ex2". Para remover diretórios é só usar rmdir (remove directory) ao invés de rm.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/plhxzl9u9ja43psv0zyo.gif)


Espero ter poupado algumas pesquisas e que agora você consiga desenrolar melhor nosso querido Linux, até a próxima. 😉

## Comandos Úteis

### mkdir
Cria um diretório, junto com ele pode ser usado:

* -p - cria uma estrutura de arquivos (mkdir -p ex4 ex5 ex6, o ex 6 vai estar dentro do ex5, que estará dentro do ex4)

### touch
Para criar arquivos, junto dele há também:

* -a - altera a hora de acesso do arquivo
* -m - altera a hora de modificação do arquivo
* -am - altera a hora de acesso e modiicação
* -c - altera a hora de acesso sem criar um novo arquivo

Podemos gerar nomes automaticos usando as chaves ({}) enquanto criamos varios arquivos 

### ls
Lista o que tem na pasta, acompanhado de:

* -a - mostra todos os arquivos, até os ocultos
* -A - mostra todos os arquivos exceto o corrente ou o acima (. , ..)
* -i - mostra o número do inode de cada arquivo
* -l - mostra permissões, número de links, propietário, grupo, tamanho, data de modificação e nome do arquivo
* -m - mostra os arquivos em sequência na mesma linha
* -n mostra permissões, número de links, UID, GID, tamanho, data de modiicação e nome do arquivo
* -o - mostra permissões, número de links, proprietário, tamanho, data de modificação e nome do arquivo
* -p - mostra uma barra na frente de nomes de diretórios
* -r - ordem reversa

### df
A "junção" de ls com -la, mostra o espaço livre/ocupado de cada partição, junto de:

* -a - inclui sistema de arquivos com zero blocos
* -h - mostra o espaço livre/ocupado em MB, KB, GB em vez de bloco
* -k - lista em kbyts
* -l - lista sistema de arquivo LOCAIS 
* -m - lista em mbytes
* -t - lista o tipo de sistema de arquivos de cada partição

### cat
Permite criar, unir e exibir arquivos, quando acompanhado de:

* -E - marca o término de linha com $
* -n - mostra a quatidade de linhas no arquivo
* -v - exibe caracteres não exibíveis (tipo acento)
* -T - exibe tabulação mostradas como ^|
* -s - remove linhas repetidas em branco
* -b - numera as linhas que tem algum conteúdo
* tac - exibe o conteúdo do arquivo em ordem contrária

### ps
Exibe informações sobre os processos que estão executando, pode ser seguido de:

* -a - mostra o processo de todos os usuários
* -A ou -e - mostra todos os processos
* -f - mostra a árvore de execução de comandos
* -g - mostra os processos de um determinado grupo
* -x - mostra os processos que não foram iniciados no console
* -u - fornece o nome do user e a hora de início do processo

### kill
Finaliza tarefas dentro do Sistema Operacional, suas variações são:

* pkill - especifica o nome do processo ou um padrão para encontrá-lo
* killall - encerrar o processo pelo nome, não funciona com nome parcial então é mais seguro que o pkill
* kill -9 - Muitas vezes não conseguimos matar o processo quando o programa trava e para termos certeza de que conseguiremos finalizá-lo, forçando a finalização, podemos usar o modificador -9 para o comando kill 

### cd
Para navegar para qualquer lugar do sistema, ele tem também:

* cd .. - sair do diretório
* cd - - volta para o último diretório acessado
* cd /diretorio - partindo da raiz ate o último diretorio passado como referência
* cd diretorio - do local corrente ate o diretório passado como referência

### path absoluto e path relativo

path absoluto é o path cujo início é a raiz do sistema (diretorio /), já no path relativo o início é o diretório ocorrente, então não precisa informar o caminho a partir do /

### pwd
Informa o diretório corrente, apresentando o caminho desde o diretório raiz até o atual.

### cp
Comando copiar, podem acompanhá-lo:

* -r - copiar um diretório
* -i - pergunta se desejamos sobrescrever um arquivo já existente
* -n - não sobrescreve um arquivo ja existente
* -r, -R - copia diretórios de forma recursiva
* -p - preserva as permissões originais do arquivo

### mv
Para mover ou renomear, caso venha seguido de:

* -b - cria um backup de cada arquivo destino existente
* -f - apaga destinos existentes sem perguntar ao user
* -i - pergunta se desejamos sobrescrever o arquivo destino já existente
* -n - não sobrescreve um arquivo destino já existente

### rm
Remover, junto de:

* -f - ignora arquivos existentes e não pergunta antes de remover
* -r, -R - remove diretórios e seus conteúdos recursivamente
* -d, --dir - remove somente diretórios vazios
* -i - pergunta se queremos remover o arquivo/diretório antes de excluir

### tar
Tem a função de compactar e descompactar aquivos, seguido de:

* -r - inserir arquivos em um .tar mesmo depois de compactado
* -c - utilizada para extração ser feita em outro diretório
dentro do tar

 Outros exemplos:
* .tar -c - cria um novo arquivo .tar
* .tar -v - mostra uma descrição do progresso de compactação
* .tar -f - nome do arquivo
* .tar.bz2 - maior compactação quando comparado com o gzip, mas leva mais tempo para compressão e descompactação
* -j - para gerar um arquivo .tar.bz2




