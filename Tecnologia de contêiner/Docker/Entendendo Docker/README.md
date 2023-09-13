# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Entendendo Docker

[![Docker](./images/Docker.png "Docker")](./images/Docker.png "Docker")

- [Mundo Docker (Cristiano Diedrich)](#mundo-docker-cristiano-diedrich "Mundo Docker (Cristiano Diedrich)")
- [Primeiros Passos com Docker: Conceitos Básicos à Criação de sua Primeira Imagem](#primeiros-passos-com-docker-conceitos-b%C3%A1sicos-%C3%A0-cria%C3%A7%C3%A3o-de-sua-primeira-imagem "Primeiros Passos com Docker: Conceitos Básicos à Criação de sua Primeira Imagem")

---

## Mundo Docker (Cristiano Diedrich)

[![docker-filesystems-busyboxrw](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-busyboxrw.png?raw=true "docker-filesystems-busyboxrw")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-busyboxrw.png?raw=true "docker-filesystems-busyboxrw")

Olá pessoal!

Para você que está começando a ler nossos posts agora, sugiro que leia antes esse e esse link que explicam o que é o Docker e como ele funciona. Hoje nós abordaremos um dos assuntos mais importantes dentro do Docker: O Filesystem.

O sistema de arquivos do Docker é chamado de layered, ou seja, é um sistema de arquivo em camadas, o que isso quer dizer?

Um sistema de arquivo comum, possui basicamente duas camadas:

**bootfs**: Onde ficam o sistema de Boot do sistema e o Kernel.

**rootfs**: Inclui o sistema de arquivo do sistema, incluindo a arquitetura de diretório, em sistemas unix-like: `/dev`, `/proc`, `/bin`, `/etc`, `/lib`, `/usr`, e `/tmp` assim como os arquivos de configuração e binários do sistema.

Quando o sistema é iniciado ele carrega o rootfs primeiramente em modo somente leitura, verifica sua integridade e em seguida remonta-o como leitura/escrita e assim fica disponível para o usuário/aplicação.

No Docker temos essa arquitetura também, mas com um diferencial, a camada de escrita que o processo/aplicação visualiza não é o mesmo rootfs base, e sim uma camada de abstração do rootfs, isso é o que faz com que um container torne-se portável, pois as modificações realizadas não são aplicadas ao sistema origem do container, e sim na camada a qual o sistema visualiza.

Para ficar mais claro, veja na figura abaixo como é um sistema tradicional:

[![docker-filesystems-generic1](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-generic1-300x225.png?raw=true "docker-filesystems-generic1")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-generic1-300x225.png?raw=true "docker-filesystems-generic1") 

Agora veja como é o filesystem no docker:

[![docker-filesystems-multiroot](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-multiroot-300x225.png?raw=true "docker-filesystems-multiroot")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-multiroot-300x225.png?raw=true "docker-filesystems-multiroot") 

Como podem notar o bootfs em vez de ser único por sistema/container, é compartilhado entre eles, mas o rootfs é isolado por camadas, ou seja, o que deve ser em comum entre o host e container é compartilhado via AUFS, que monta uma camada de leitura/escrita em cima do filesystem em somente leitura, isso garante que modificações feitas dentro do container não afetem o sistema de arquivos do host.

A imagem abaixo ilustra melhor como funciona essas camadas:

[![docker-filesystems-busyboxrw](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-busyboxrw-300x225.png?raw=true "docker-filesystems-busyboxrw")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-busyboxrw-300x225.png?raw=true "docker-filesystems-busyboxrw")

Um detalhe nessa arquitetura é que a cada modificação e commit do container é gerada uma nova camada, ou seja, digamos que eu inicie um container a partir de uma imagem do Debian, e instale o serviço apache dentro desse container, quando eu for transformar esse container em uma imagem, essa imagem possuirá a primeira camada que é do sistema Debian, e uma camada adicional que refere-se a instalação do serviço apache. Na imagen abaixo podemos visualizar melhor esse ambiente.

[![docker-filesystems-multilayer-update](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-multilayer-update-300x241.png?raw=true "docker-filesystems-multilayer-update")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystems-multilayer-update-300x241.png?raw=true "docker-filesystems-multilayer-update")

Lembrando que uma imagem pode ser utilizada diversas vezes, ou seja, há compartilhamento da imagem entre os containers, mas os containers depois de iniciados são isolados uns dos outros, na imagem abaixo podemos visualizar essa arquitetura.

[![docker-filesystem](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystem-300x169.jpg?raw=true "docker-filesystem")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/docker-filesystem-300x169.jpg?raw=true "docker-filesystem")

Como podemos notar, há o compartilhamento das camadas inferiores, pois elas fazem parte da imagem que originou o container, e a camada de escrita, que faz parte do container rodando, é isolada para cada container.

Por hoje é isso, veremos em breve um pouco mais sobre filesystem no Docker, e algumas outras questões relacionadas a essa arquitetura. Ficou com dúvida? Gostaria de saber mais? Algum feedback a nos dar? Deixe sua mensagem e vamos conversando.

Abraço!

[![Cristiano](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/cristiano.png?raw=true "Cristiano")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Mundo%20Docker%20(Cristiano%20Diedrich)/cristiano.png?raw=true "Cristiano")

> ## Cristiano Diedrich
>
> Entusiasta Open Source, seu principal foco é ir atrás de > ideias novas e torna-las realidade através de soluções simples e eficientes, o menos é mais, e o dividir é multiplicar.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--entendendo-docker "Subir para o topo")

---

## Primeiros Passos com Docker: Conceitos Básicos à Criação de sua Primeira Imagem

Nos últimos tempos você já deve ter ouvido falar de Docker, de containers ou acabou se deparando com um arquivinho sem vergonha chamado Dockerfile na raiz do seu projeto. Mas o que tudo isso significa e como funciona?

Docker é uma plataforma voltada para a criação e execução de containers. Diferente de uma VM, um container empacota somente o código, dependências e variáveis de ambiente necessárias para a execução de uma aplicação. Sendo assim, ao invés de termos uma infraestrutura onde cada VM tem seu próprio SO sendo responsável por uma aplicação diferente, temos uma infraestrutura onde, com apenas um sistema operacional e através do Docker, podemos gerenciar diversas aplicações. Cada uma dessas aplicações é executada de forma isolada, sem a necessidade de um sistema operacional próprio.

[![Containers x VMs](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/0-ZvHUVaVlXV7-Nygn.png?raw=true "Containers x VMs")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/0-ZvHUVaVlXV7-Nygn.png?raw=true "Containers x VMs")

Para um container ser criado, ele necessita de uma imagem: o básico para a aplicação ser executada, desde bibliotecas até variáveis de ambiente. Essas imagens são criadas através de um Dockerfile e podem ser baixadas e publicadas em diversos registries, sendo o mais famoso deles o Docker Hub. A imagem abaixo nos mostra um resumo do fluxo da estrutura do Docker e de como esses componentes se relacionam entre si.

[![Funcionamento básico do Docker](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/0%20SWHyvx_VdWQluT31.png?raw=true "Funcionamento básico do Docker")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/0%20SWHyvx_VdWQluT31.png?raw=true "Funcionamento básico do Docker")

Meio confuso, né? Para entender melhor como esse fluxo funciona, vamos começar com um pouco de prática, seguindo alguns passos:

1. **Instalar o Docker**

A instalação para distribuições Linux pode ser feita [aqui](https://github.com/docker/docker-install "Clique para acessar o GitHub do docker-install"). Uma vez feito o download, basta conferir a versão com o seguinte comando:

```bash
docker --version
```

2. **Fazendo download de imagens**

Para fazer o download de uma imagem, usamos o comando `docker pull`, passando como argumento o nome da imagem que queremos baixar. Essas imagens são baixadas de um `registry`, que funciona como plataforma de compartilhamento dessas mesmas imagens. Uma vez cadastrado no registry, o usuário pode fazer download e alterar essas mesmas imagens conforme sua necessidade.

Nesse exemplo, vamos utilizar o registry padrão do Docker, o `DockerHub`. Cada imagem nessa plataforma é identificada da seguinte forma:

*nome-do-usuario/nome-da-imagem*

Todavia, imagens oficiais não seguem esse padrão, sendo identificadas apenas pelo seu nome. Se pesquisarmos por “node”, encontraremos mais de 50 mil resultados, sendo o primeiro deles a imagem oficial:

[![NodeJS](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/1-0ewhkffWuIlFJHuliMOP5g.png?raw=true "NodeJS")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/1-0ewhkffWuIlFJHuliMOP5g.png?raw=true "NodeJS")

Se irmos um pouco mais abaixo na listagem, poderemos ver outra imagem do Node pertencente ao usuário nodejsn, sendo identificado seu nome antes do nome da própria imagem:

[![NodeJSN / Node](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/1-QRZ6dIf_WOz-4rEayBGBjw.png?raw=true "NodeJSN / Node")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/1-QRZ6dIf_WOz-4rEayBGBjw.png?raw=true "NodeJSN / Node")

Se acessarmos a página da imagem oficial do Node, encontraremos o comando para fazer download da imagem:

[![Node - Docker pull node](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/1-cOgrRELYRCV2ClNY9pTDcQ.png?raw=true "Node - Docker pull node")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/1-cOgrRELYRCV2ClNY9pTDcQ.png?raw=true "Node - Docker pull node")

Mas o que de fato vai acontecer se eu rodar esse comando?

Ao receber o comando `pull` sem uma versão específica, o docker client pede para docker daemon verificar se já temos a versão mais recente da imagem em nossa máquina. Se a imagem não existir no repositório local (nosso caso), ele vai buscar em seu registry padrão pelo nome que passamos por parâmetro e então, se existir uma imagem com o nome passado, irá realizar o download nos fornecendo a seguinte saída:

[![Download newer image for node](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/1-ovqeGKMtuZEFBKV0fTGYFg.png?raw=true "Download newer image for node")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/1-ovqeGKMtuZEFBKV0fTGYFg.png?raw=true "Download newer image for node")

3. **Criando imagens**

Através de um `Dockerfile`, podemos criar uma nova imagem usando outra como base. Também é possível especificar uma série de comandos para criar estruturas específicas para o deploy de nossas aplicações. O arquivo abaixo é um exemplo de Dockerfile para uma aplicação básica escrita em JavaScript.

```bash
FROM node

ENV NODE_ENV=production

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY index.js index.js

EXPOSE 8080

CMD ["node","index.js"]
```

Cada um dos comandos acima exerce uma função diferente:

- **FROM** especifica a imagem base que será usada;

- **ENV** declara uma variável de ambiente;

- **RUN** executa um comando;

- **WORKDIR** muda o diretório atual (similar ao comando `cd` em um terminal);

- **COPY** copia arquivos e diretórios do host para o build da imagem (sendo o segundo argumento o nome que será usado no build);

- **EXPOSE** expõe uma porta qualquer;

- **CMD** indica o comando que será rodado para iniciar a aplicação em um container construído usando essa imagem.

```bash
const http = require('http');


http.createServer((request, response) => {
    response.setHeader('Content-Type', 'text/html');
    response.write('<h1>Muito bem! Aprenda mais sobre Docker nas <a href="https://docs.docker.com/">docs</a></h1>'
    + '<img src="https://media2.giphy.com/media/mGK1g88HZRa2FlKGbz/giphy.gif" alt="Gif de duas pessoas aplaudindo">');
    response.end();
}).listen(8080);

console.log('Server running at http://localhost:8080/');
```

Usando o arquivo acima conseguiremos ver o processo em ação. Basta copiar para um diretório de sua escolha e nomeá-lo para `index.js`. Feito isso, rodaremos o seguinte comando:

```bash
docker image build -t node-app .
```

Com o comando acima estamos indicando para o docker construir uma imagem utilizando uma tag para identificá-la como a última versão criada da imagem `node-app` e dizendo que o Dockerfile necessário para construir a imagem está no diretório atual. Após esse comando ser executado, poderemos montar um container usando a imagem gerada.

4. **Usando uma imagem para executar um container**

Tendo nosso Dockerfile criado e nossa imagem criada, basta executar o comando abaixo para a mágica acontecer:

```bash
docker container run -d -p 80:8080 node-app
```

Com esse comando, estamos basicamente dizendo ao Docker “crie um container (docker container run) que rode no background, sem ocupar meu terminal atual (-d), mapeando uma porta local para uma outra exposta no container (-p 80:8080) e usando a imagem node-app”. Caso a imagem não exista, o docker daemon fará uma busca pelo nome em algum registry.

Agora basta seguir a documentação do Docker para aprender muitas outras possibilidades para montar imagens e configurar containers. Por fim, não se esqueçam de acessar o `localhost` e ver o resultado dos quatro passos que seguimos ao longo desse artigo.

[![Written by Leonardo Berlatto](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/Leonardo%20Berlatto.png?raw=true "Written by Leonardo Berlatto")](https://github.com/systemboys/React_Codes/blob/main/Tecnologia%20de%20cont%C3%AAiner/Docker/Entendendo%20Docker/images/Leonardo%20Berlatto/Leonardo%20Berlatto.png?raw=true "Written by Leonardo Berlatto")

> Software Engineering student at PUCRS and DevOps enthusiast.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--entendendo-docker "Subir para o topo")

---