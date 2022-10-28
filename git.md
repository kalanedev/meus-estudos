Git 

O Git serve para gerenciar projetos, é nele que você controla as versões.
No github você mostra seus projetos, ele manda para a nuvem e permite que outras pessoas vejam.
Para começar a aprender os comandos é necessário saber que:
*commitar - confirmar as alterações feitas no commit;
*merge - mesclar. é para juntar a branch;
*main - é o nome que costuma ser dado para o projeto inteiro.

Indo para os comandos:
git clone - clona o repositório inteiro, e para usá-lo colocamos logo em seguida o link do repositório que queremos clonar;
git init - com ele inicializamos um repositório;
git add - adiciona a alteração do arquivo ao com;mit
git commit -m - descreve e salva o que foi feito naquele projeto, ele vem seguido de "" e dentro delas a descrição do que foi feito;
git branch -M - faz como se fosse uma ramificação. Ele divide em partes, assim uma pessoa pode cuidar de uma parte enquanto outra cuida de outra.

Até aí, seu projeto está apenas na sua máquina, e a partir daí começamos a colocá-lo do github da seguinte forma:
git remote add origin - diz para onde as alterações vão. para isso colocamos o comando, e o link do github em que o repositório está;
git push origin main - envia para a nuvem. lembrando que origin é porque foi o nome dado no comando do remote e main para juntar a branch;
git pull origin main - "puxa" as alterações que eu ainda não tenho na minha máquina. 