# Estudos 
Nesse repositório vou colocar todas as minhas anotações de estudos para fixar conhecimento e poder praticar mais. Espero que possa ajudar outros iniciantes e que fique registrada minha evolução. :)

### Sumário - Git
Aqui temos alguns comandos de git.


## 1. Git 
O Git serve para gerenciar projetos, é nele que você controla as versões.

No github você mostra seus projetos, ele manda para a nuvem e permite que outras pessoas vejam. Para começar a aprender os comandos é necessário saber que:
- **commitar** - confirmar as alterações feitas no commit;
- **merge** - mesclar. é para juntar a branch;
- **main** - é o nome que costuma ser dado para o projeto inteiro.

## 2. Comandos do Git
- `git init` - com ele inicializamos um repositório;
- `git clone <url_repo>` - clona o repositório inteiro, e para usá-lo colocamos logo em seguida o link do repositório que queremos clonar;
- `git add` - adiciona a alteração do arquivo ao commit;
- `git commit -m "first  commit"` - descreve e salva o que foi feito naquele projeto, ele vem seguido de "" e dentro delas a descrição do que foi feito;
- `git branch -M myBranch` - faz como se fosse uma ramificação. Ele divide em partes, assim uma pessoa pode cuidar de uma parte enquanto outra cuida de outra;

## 3. GitHub
Até aí, seu projeto está apenas na sua máquina, e a partir daí começamos a colocá-lo no GitHub da seguinte forma:
+ `git remote add origin` - diz para onde as alterações vão. para isso colocamos o comando, e o link do GitHub em que o repositório está;
+ `git push origin main` - envia para a nuvem. lembrando que origin é porque foi o nome dado no comando do remote e main para juntar a branch;
+ `git pull origin main` - "puxa" as alterações que eu ainda não tenho na minha máquina. 