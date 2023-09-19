# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Hospedar aplicativo ReactJS em servidor de hospedagem

[![Hospedagem](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/Hospedar%20aplicativo%20ReactJS%20em%20servidor%20de%20hospedagem/images/hospedagem-de-sites-destaque-2.png?raw=true "Hospedagem")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/Hospedar%20aplicativo%20ReactJS%20em%20servidor%20de%20hospedagem/images/hospedagem-de-sites-destaque-2.png?raw=true "Hospedagem")

##### Hospedagem de projeto
- [Hospedagem de projeto em ReactJS](#hospedagem-de-projeto-em-reactjs "Hospedagem de projeto em ReactJS")
- [Se suas API's estiverem hospedadas em outro servidor](#se-suas-apis-estiverem-hospedadas-em-outro-servidor "Se suas API's estiverem hospedadas em outro servidor")
##### AWS, Docker e Contêiners
- [Hospedando uma build do ReactJS em uma instância AWS usando Docker e Debian Linux](#hospedando-uma-build-do-reactjs-em-uma-inst%C3%A2ncia-aws-usando-docker-e-debian-linux "Hospedando uma build do ReactJS em uma instância AWS usando Docker e Debian Linux")
- [Gerenciando contêineres Docker: Parar, reiniciar e remover contêineres](#gerenciando-cont%C3%AAineres-docker-parar-reiniciar-e-remover-cont%C3%AAineres "Gerenciando contêineres Docker: Parar, reiniciar e remover contêineres")
- [Renomeando um contêiner Docker sem reiniciar: Como atualizar o nome do contêiner sem interromper a execução](#renomeando-um-cont%C3%AAiner-docker-sem-reiniciar-como-atualizar-o-nome-do-cont%C3%AAiner-sem-interromper-a-execu%C3%A7%C3%A3o "Renomeando um contêiner Docker sem reiniciar: Como atualizar o nome do contêiner sem interromper a execução")
#### Docker Compose
- [Hospedar sua build em ReactJS na AWS utilizando Docker Compose](#hospedar-sua-build-em-reactjs-na-aws-utilizando-docker-compose "Hospedar sua build em ReactJS na AWS utilizando Docker Compose")
- [Tutorial passo a passo para limpar e iniciar serviços Docker com Docker Compose](#tutorial-passo-a-passo-para-limpar-e-iniciar-serviços-docker-com-docker-compose "Tutorial passo a passo para limpar e iniciar serviços Docker com Docker Compose")
- [Procedimento para Docker Compose para efeito de parar e executar os serviços](#procedimento-para-docker-compose-para-efeito-de-parar-e-executar-os-servi%C3%A7os "Procedimento para Docker Compose para efeito de parar e executar os serviços")
  > **( i )** Docker Compose simplificado.
  - [Guia Passo a Passo: Como Dockerizar e Orquestrar Aplicação Frontend e Backend com Docker Compose na AWS](#guia-passo-a-passo-como-dockerizar-e-orquestrar-aplica%C3%A7%C3%A3o-frontend-e-backend-com-docker-compose-na-aws "Guia Passo a Passo: Como Dockerizar e Orquestrar Aplicação Frontend e Backend com Docker Compose na AWS")
  - [Como Derrubar (Parar) Sua Aplicação Dockerizada com Docker Compose](#como-derrubar-parar-sua-aplica%C3%A7%C3%A3o-dockerizada-com-docker-compose "Como Derrubar (Parar) Sua Aplicação Dockerizada com Docker Compose")
  - [Script Bash para Gerenciar o Ciclo de Vida de Aplicações Docker Compose](#script-bash-para-gerenciar-o-ciclo-de-vida-de-aplica%C3%A7%C3%B5es-docker-compose "Script Bash para Gerenciar o Ciclo de Vida de Aplicações Docker Compose")
  - [Destaque: Estrutura de Arquivos para Implantação Docker de Aplicação Frontend e Backend](#destaque-estrutura-de-arquivos-para-implanta%C3%A7%C3%A3o-docker-de-aplica%C3%A7%C3%A3o-frontend-e-backend "Destaque: Estrutura de Arquivos para Implantação Docker de Aplicação Frontend e Backend")
  - [Seleção Automática da URL de API com Base no Ambiente em JavaScript](#sele%C3%A7%C3%A3o-autom%C3%A1tica-da-url-de-api-com-base-no-ambiente-em-javascript "Seleção Automática da URL de API com Base no Ambiente em JavaScript")

---

## Hospedagem de projeto em ReactJS

Existem várias opções de provedores de hospedagem na nuvem que oferecem suporte para aplicativos ReactJS, tais como AWS (Amazon Web Services), Google Cloud, Azure, DigitalOcean, entre outros. Esses provedores de hospedagem oferecem várias opções de hospedagem, desde máquinas virtuais até contêineres e serviços gerenciados.

O processo geral para hospedar um aplicativo ReactJS envolve alguns passos básicos:

1. Construir o aplicativo para produção: Você precisa criar uma versão otimizada do seu aplicativo para produção. Para fazer isso, basta executar o comando `npm run build` no diretório do projeto. Isso criará uma pasta "build" com os arquivos necessários para executar o aplicativo.

2. Escolher um provedor de hospedagem: Existem várias opções de provedores de hospedagem na nuvem. É importante considerar as necessidades do seu aplicativo e escolher um provedor que ofereça recursos e serviços que atendam às suas necessidades.

3. Provisionar recursos: Depois de escolher um provedor de hospedagem, você precisa provisionar os recursos necessários, como máquinas virtuais, contêineres, banco de dados, etc. Cada provedor tem sua própria interface para provisionar recursos, portanto, é importante seguir as instruções do provedor escolhido.

4. Configurar o servidor web: Depois de provisionar os recursos, você precisa configurar o servidor web para hospedar seu aplicativo ReactJS. Isso geralmente envolve configurar um servidor web como Nginx ou Apache, e configurá-lo para servir os arquivos do aplicativo ReactJS.

5. Publicar o aplicativo: Finalmente, você precisa publicar os arquivos do aplicativo ReactJS no servidor web. Isso geralmente envolve copiar os arquivos do diretório "build" para o diretório raiz do servidor web.

Esses são apenas os passos básicos envolvidos na hospedagem de um aplicativo ReactJS. Cada provedor de hospedagem tem sua própria documentação e guias para ajudá-lo a configurar e implantar seu aplicativo. É importante seguir as instruções do provedor escolhido e garantir que o aplicativo esteja configurado corretamente antes de colocá-lo em produção.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Se suas API's estiverem hospedadas em outro servidor

Se a sua API estiver hospedada em outro servidor, você precisará atualizar as configurações da sua aplicação ReactJS para apontar para a nova URL da API. Isso pode ser feito em um arquivo de configuração separado, como um arquivo `.env`, que é carregado durante o processo de compilação. Você pode definir a URL da API nesse arquivo, e em seguida, fazer referência a essa variável em seus componentes ReactJS.

Por exemplo, suponha que a URL da API seja `http://localhost:3000`. Você poderia definir uma variável de ambiente chamada `REACT_APP_API_URL` em um arquivo `.env` na raiz do seu projeto ReactJS, da seguinte forma:

```javascript
REACT_APP_API_URL=http://localhost:3000
```

Em seguida, em seus componentes ReactJS, você poderia se referir a essa variável usando `process.env.REACT_APP_API_URL`. Por exemplo:

```javascript
axios.get(`${process.env.REACT_APP_API_URL}/users`)
  .then(response => {
    // faça algo com os dados da resposta
  })
  .catch(error => {
    // lide com o erro
  });
```

Ao fazer isso, sua aplicação ReactJS deve ser capaz de se comunicar com a API, independentemente de onde ela esteja hospedada.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Hospedando uma build do ReactJS em uma instância AWS usando Docker e Debian Linux

Para hospedar os arquivos de sua build do ReactJS em uma instância AWS com Debian Linux, você pode seguir os seguintes passos:

1. Conectar-se à instância: Use um cliente SSH, como o OpenSSH, para se conectar à instância AWS usando seu endereço IP público e as credenciais SSH associadas à instância.

2. Instalar o Docker: Se você ainda não tiver o Docker instalado na instância, siga as etapas mencionadas anteriormente para [instalar o Docker](https://github.com/systemboys/React_Codes/tree/main/Tecnologia%20de%20cont%C3%AAiner/Docker#instala%C3%A7%C3%A3o-do-docker-no-debian-linux-e-ubuntu "instalar o Docker") no Debian Linux.

3. Clonar o repositório do GitHub: No diretório desejado da instância, clone o repositório do GitHub que contém sua build do ReactJS. Você pode usar o comando `git clone` com a URL do repositório, como:

```bash
git clone https://github.com/github_account/your_build.git
```

Isso criará uma cópia do repositório em sua instância.

4. Construir a imagem do Docker: Dentro do diretório clonado, crie um arquivo Dockerfile para criar uma imagem Docker para sua build do ReactJS. O Dockerfile pode ter o seguinte conteúdo:

```bash
# Use a imagem do Nginx como base
FROM nginx

# Copie os arquivos da build para o diretório de trabalho padrão do Nginx
COPY . /usr/share/nginx/html

# Exponha a porta 80 para tráfego externo
EXPOSE 80
```

Salve o Dockerfile no diretório raiz da sua build do ReactJS.

5. Construir e executar o contêiner Docker: No diretório raiz da sua build, execute o seguinte comando para construir a imagem Docker:

```bash
docker build -t my-react-app .
```

Isso criará a imagem Docker com base no Dockerfile.

Agora, você pode executar o contêiner com o seguinte comando:

```bash
docker run -d -p 80:80 my-react-app
```

O contêiner será executado e estará disponível na porta 80 da sua instância AWS.

> ( ! ) Observação!
>
> No comando `docker run -d -p 80:80 my-react-app`, o termo "my-react-app" é o nome ou a tag da imagem Docker que você deseja executar como um contêiner.
>
> Uma imagem Docker é uma representação imutável de um aplicativo ou ambiente pré-configurado. Ela contém todos os componentes necessários para executar um aplicativo, incluindo o sistema operacional, bibliotecas, dependências e o próprio aplicativo.
>
> Quando você executa o comando `docker run`, você está criando uma instância em execução de uma imagem Docker. A opção `-d` indica que o contêiner será executado em segundo plano (modo detached). A opção `-p 80:80` mapeia a porta 80 do contêiner para a porta 80 do host, permitindo que o aplicativo dentro do contêiner seja acessível através da porta 80 do host.
>
> O termo "my-react-app" é usado como o nome da imagem Docker que será executada como um contêiner. Geralmente, esse nome é definido durante o processo de criação da imagem Docker ou ao fazer o push da imagem para um registro de contêiner, como o Docker Hub.
>
> Você pode escolher qualquer nome ou tag para a imagem Docker que esteja de acordo com sua convenção de nomenclatura. Essa nomenclatura facilita a identificação e o gerenciamento das imagens Docker em seu ambiente.

Agora você pode acessar o seu portal de notícias ReactJS na instância AWS através do endereço IP público da instância. Basta digitar o endereço IP público no navegador e você deverá ver o seu aplicativo sendo hospedado na instância AWS.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Gerenciando contêineres Docker: Parar, reiniciar e remover contêineres

O código criptografado que você vê após executar o comando "docker run" é o ID do contêiner Docker que foi criado. Esse ID é exclusivo para cada contêiner em execução.

Após fechar a sessão SSH e se conectar novamente à instância no futuro, você pode visualizar o ID do contêiner executando o comando `docker ps` ou `docker ps -a` no terminal. O comando `docker ps` lista apenas os contêineres em execução no momento, enquanto o comando `docker ps -a` lista todos os contêineres, incluindo os que estão parados.

O ID do contêiner é usado para identificar o contêiner dentro do Docker e realizar várias operações, como parar, reiniciar ou remover o contêiner. É útil ter esse ID registrado para gerenciar o contêiner posteriormente.

Além disso, se você atribuiu um nome ao contêiner durante a execução do comando `docker run`, pode usar o nome em vez do ID para se referir ao contêiner em operações futuras.

Espero que isso esclareça sua dúvida! Se você tiver mais perguntas, fique à vontade para perguntar.

> Comandos do Docker

Aqui está uma lista dos principais comandos do Docker para parar, reiniciar e remover contêineres:

1. Parar um contêiner em execução:

```bash
docker stop <container_id>
```
Substitua `<container_id>` pelo ID ou nome do contêiner que você deseja parar. Isso irá interromper a execução do contêiner de forma controlada.

2. Iniciar um contêiner parado:

```bash
docker start <container_id>
```
Substitua `<container_id>` pelo ID ou nome do contêiner que você deseja iniciar. Isso irá iniciar um contêiner que foi previamente parado.

3. Reiniciar um contêiner:

```bash
docker restart <container_id>
```
Substitua `<container_id>` pelo ID ou nome do contêiner que você deseja reiniciar. Isso irá parar e, em seguida, iniciar novamente o contêiner.

4. Remover um contêiner:

```bash
docker rm <container_id>
```
Substitua `<container_id>` pelo ID ou nome do contêiner que você deseja remover. Certifique-se de que o contêiner esteja parado antes de executar esse comando. Se o contêiner estiver em execução, você pode adicionar a opção `-f` para forçar a remoção.

5. Parar todos os contêineres em execução:

```bash
docker stop $(docker ps -aq)
```
Este comando para todos os contêineres em execução na sua máquina. A opção `$(docker ps -aq)` lista todos os IDs de contêineres em execução, que são passados como argumento para o comando `docker stop`.

6. Remover todos os contêineres parados:

```bash
docker rm $(docker ps -aq)
```
Este comando remove todos os contêineres parados na sua máquina. A opção `$(docker ps -aq)` lista todos os IDs de contêineres, incluindo os parados, que são passados como argumento para o comando `docker rm`.

Lembre-se de substituir `<container_id>` pelo ID ou nome real do contêiner que você deseja operar. Além disso, tome cuidado ao remover contêineres, pois isso é uma ação irreversível e todos os dados do contêiner serão perdidos.

Esses são os comandos básicos para parar, reiniciar e remover contêineres no Docker. Existem outros comandos disponíveis para gerenciar contêineres e explorar diferentes opções. Você pode consultar a documentação oficial do Docker para obter mais informações sobre esses comandos e suas opções.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Renomeando um contêiner Docker sem reiniciar: Como atualizar o nome do contêiner sem interromper a execução

Ao renomear um contêiner Docker, você estará alterando o nome do contêiner na coluna "NAMES" da saída do comando `docker ps`. O nome original do contêiner é gerado automaticamente pelo Docker ou pode ser especificado manualmente durante a criação do contêiner.

No exemplo que você forneceu, o nome atual do contêiner é "serene_shamir". Se você deseja renomeá-lo para "Jornal de Mirador", você pode usar o comando `docker rename` da seguinte maneira:

```bash
docker rename serene_shamir New_Name
```

Isso alterará o nome do contêiner de "serene_shamir" para "New_Name". Após executar esse comando, se você usar o comando `docker ps`, verá a coluna "NAMES" atualizada com o novo nome do contêiner.

Lembre-se de que o nome do contêiner deve ser exclusivo no contexto do Docker na sua máquina. Portanto, certifique-se de que o novo nome não esteja sendo usado por outro contêiner existente.

Espero que isso esclareça sua dúvida! Se você tiver mais perguntas, fique à vontade para perguntar.

> É preciso reiniciá-lo?

Não é necessário reiniciar o contêiner após renomeá-lo. A alteração do nome do contêiner não afeta sua execução ou estado atual. O contêiner continuará em execução normalmente, mantendo seu estado, conexões e quaisquer configurações existentes.

A mudança de nome é apenas uma atualização no metadado do contêiner e não requer uma reinicialização para ser aplicada. Você pode verificar isso executando o comando `docker ps`, e verá que o nome do contêiner foi atualizado na coluna "NAMES".

Portanto, não é necessário reiniciar o contêiner após renomeá-lo. O contêiner continuará funcionando com o novo nome normalmente, mantendo seu estado atual.

Lembre-se de que, se você estiver usando o nome do contêiner para se referir a ele em outros comandos Docker ou scripts, deverá atualizar essas referências com o novo nome para evitar erros.

Espero que isso esclareça sua dúvida! Se você tiver mais perguntas, estou aqui para ajudar.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Hospedar sua build em ReactJS na AWS utilizando Docker Compose

Entre no diretório do seu projeto e gere sua build:

```bash
npm run build
```

> ( ! ) Faça isso no diretório de suas APIs também caso tenha!

Renomei suas buils. Exemplo:

```bash
./api/
./frontend/
```

Crie um diretório para produção, `./prod/` é um nome sugestivo. Coloque as duas builds renomeadas dentro de seu diretório `./prod/`, deverá ter a seguinte estrutura:

```bash
./prod/
	./api/
	./frontend/
```

Crie e edite os arquivos `Dockerfile` dentro dos dois diretórios `./prod/api/` e `./prod/frontend/` e coloque os seguintes conteúdos:

### Arquivo `./prod/api/Dockerfile`

```bash
# Use uma imagem base com Node.js
FROM node:buster

# Defina o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copie o package.json e package-lock.json para o diretório de trabalho
COPY package*.json ./

RUN npm install -g npm@9.7.2

# Instale as dependências do projeto
RUN npm install

# Copie o código-fonte para o diretório de trabalho
COPY . .

# Exponha a porta do servidor backend (ajuste para a porta correta)
EXPOSE 3333

# Inicie o servidor backend quando o contêiner for iniciado
CMD ["npm", "run", "dev"]
RUN npx prisma generate
```

### Arquivo `./prod/frontend/Dockerfile`

```bash
# Use uma imagem base com Node.js
FROM node:14-alpine

# Defina o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copie o código-fonte para o diretório de trabalho
COPY . .

# Use uma imagem Nginx para o ambiente de produção
FROM nginx:1.21-alpine

# Copie os arquivos de build do frontend para o diretório padrão do Nginx
COPY . /usr/share/nginx/html

# Copie o arquivo de configuração personalizado para o diretório do Nginx
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Exponha a porta 80 para o tráfego externo
EXPOSE 80

# Inicie o servidor Nginx quando o contêiner for iniciado
CMD ["nginx", "-g", "daemon off;"]
```

Crie o arquivo `./docker-compose.yml` dentro de `./prod/` e coloque o seguinte conteúdo:

### Arquivo `./prod/docker-compose.yml`

```bash
version: '3.3'
services:
  frontend:
    build:
      context: ./frontend
      dockerfile: Dockerfile
    ports:
      - 80:80
    networks:
      - jm

  backend:
    build:
      context: ./api
      dockerfile: Dockerfile
    ports:
      - 3333:3333
    networks:
      - jm

networks:
  jm:
    driver: bridge
```

> ( ! ) Esse último arquivo `./docker-compose.yml` deve ficar dentro de "prod" apenas!

Inicie o Git dentro do seu diretório `./prod/`, suba suas builds para o GitHub, em seguida, acesse sua instância na AWS via SSH e faça o clone do seu projeto na raiz da instância:

```bash
git clone https://github.com/git-account/your-project.git
```

Entre dentro do diretório do seu projeto, execute o arquivo `docker-compose.yml`:

```bash
sudo docker-compose up -d
```

Crie o diretório `./prod/nginx` dentro de "prod" com os seguintes arquivos:

### Arquivo `./prod/nginx/default.conf`

```bash
upstream frontend {
    server frontend:3000;
}

upstream api {
    server api:3333;
}

server {
    listen 80;

    location / {
        proxy_pass http://frontend;
    }

    location /sockjs-node {
        proxy_pass http://frontend;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "Upgrade";
    }

    location /api {
        rewrite /api/(.*) /$1 break;
        proxy_pass http://api;
    }
}
```

### Arquivo `./prod/nginx/Dockerfile`

```bash
FROM nginx
COPY ./default.conf /etc/nginx/conf.d/default.conf
```

Dentro do diretório "nginx", os arquivos "default.conf" e "Dockerfile" têm os seguintes propósitos:

1. "default.conf": Este arquivo é usado para configurar o servidor web Nginx. É um arquivo de configuração específico para o Nginx e é usado para definir as diretrizes de funcionamento do servidor. O arquivo "default.conf" contém informações como as portas em que o Nginx deve escutar, as localizações dos arquivos estáticos, as configurações de proxy reverso, as regras de roteamento e outras configurações relacionadas ao servidor web.

2. "Dockerfile": O arquivo "Dockerfile" é usado para criar a imagem Docker do contêiner Nginx. Ele contém uma série de instruções que o Docker Engine segue para criar a imagem. O arquivo especifica a imagem base, as dependências necessárias, o diretório de trabalho, os comandos para copiar os arquivos necessários para a imagem, as configurações do ambiente e outras instruções para configurar o contêiner Nginx corretamente.

Em resumo, o arquivo "default.conf" é usado para configurar o servidor Nginx dentro do contêiner, enquanto o arquivo "Dockerfile" é usado para construir a imagem do contêiner Nginx com base nas configurações definidas no "default.conf". Esses arquivos são fundamentais para criar e configurar corretamente um contêiner Nginx usando o Docker.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Tutorial passo a passo para limpar e iniciar serviços Docker com Docker Compose

O código fornecido a seguir é uma sequência de comandos do Docker que realiza algumas operações comuns de gerenciamento de contêineres e imagens. Vou descrever o que cada comando faz e, em seguida, fornecer um tutorial passo a passo.

1. `docker rm $(docker ps -a -q)`: Este comando remove todos os contêineres existentes no sistema Docker. A parte `$(docker ps -a -q)` é uma subcomando que lista todos os contêineres existentes (`docker ps -a`) e retorna apenas os IDs (`-q`) dos contêineres. Esses IDs são passados para o comando `docker rm`, que remove os contêineres.

2. `docker rmi $(docker images -a -q)`: Este comando remove todas as imagens existentes no sistema Docker. Assim como o comando anterior, `$(docker images -a -q)` lista todas as imagens (`docker images -a`) e retorna apenas os IDs (`-q`) das imagens. Esses IDs são passados para o comando `docker rmi`, que remove as imagens.

3. `docker image prune`: Este comando remove todas as imagens ociosas, ou seja, imagens que não estão sendo usadas por nenhum contêiner em execução.

4. `sudo docker-compose up -d`: Este comando inicia os serviços definidos em um arquivo de configuração chamado `docker-compose.yml`. O `docker-compose` é uma ferramenta para definir e executar aplicativos Docker compostos por vários contêineres. A opção `-d` inicia os serviços em segundo plano (modo detached), ou seja, sem exibir os logs no terminal.

Aqui está um tutorial passo a passo para executar esses comandos:

Passo 1: Abra um terminal ou prompt de comando no seu sistema operacional.

Passo 2: Certifique-se de ter o Docker e o Docker Compose instalados. Se você ainda não os possui, você pode seguir as instruções de instalação fornecidas pela Docker em seu site oficial.

Passo 3: Certifique-se de ter privilégios administrativos para executar comandos Docker. O comando `sudo` usado no último comando (`sudo docker-compose up -d`) é específico para sistemas baseados em Linux. Se você estiver usando um sistema operacional diferente, pode omitir o `sudo`.

Passo 4: Navegue até o diretório onde seu arquivo `docker-compose.yml` está localizado. Certifique-se de que o arquivo esteja presente antes de continuar.

Passo 5: Execute cada comando um de cada vez, pressionando Enter após cada um deles:

```bash
docker rm $(docker ps -a -q)
docker rmi $(docker images -a -q)
docker image prune
sudo docker-compose up -d
```

Aguarde até que cada comando termine de executar antes de prosseguir para o próximo.

Após a conclusão do último comando, os contêineres existentes e as imagens serão removidos, as imagens ociosas serão limpas e os serviços definidos no arquivo `docker-compose.yml` serão iniciados em segundo plano.

Certifique-se de revisar o arquivo `docker-compose.yml` para entender quais serviços serão iniciados e quais portas ou volumes serão mapeados. Esse arquivo é crucial para a configuração do seu ambiente Docker.

> Caso deseje apagar o projeto também, saia do diretório do projeto ficando no raiz e execute o seguinte código:
> 
> ```bash
> sudo rm -rf your-project
> ```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Procedimento para Docker Compose para efeito de parar e executar os serviços

1. Gerar as builds da API e do Projeto Frontdnd:

   > Obs.: Os arquivos `./api/Dockerfile` e `./frontend/Dockerfile` e `./frontend/nginx.conf` deverão permanecer, subistituir apenas os arquivos da build!

   > ( ! ) Este procedimento foi feito e testado na aplicação do portal de notícias "Jornal de Mirador" (`https://www.jornaldemirador.com.br`).

   ***Arquivos necessários para rodar os serviços Docker:***

   1. Conteúdo do arquivo `./api/Dockerfile`:

      ```bash
      # Use uma imagem base com Node.js
      FROM node:buster
      
      # Defina o diretório de trabalho dentro do contêiner
      WORKDIR /app
      
      
      # Copie o package.json e package-lock.json para o diretório de trabalho
      COPY package*.json ./
      
      RUN npm install -g npm@9.7.2
      
      # Instale as dependências do projeto
      RUN npm install
      
      # Copie o código-fonte para o diretório de trabalho
      COPY . .
      
      # Exponha a porta do servidor backend (ajuste para a porta correta)
      EXPOSE 3333
      
      # Inicie o servidor backend quando o contêiner for iniciado
      CMD ["npm", "run", "dev"]
      RUN npx prisma generate
      ```

   2. Conteúdo do arquivo `./frontend/Dockerfile`:

      ```bash
      # Use uma imagem base com Node.js
      FROM node:14-alpine
      
      # Defina o diretório de trabalho dentro do contêiner
      WORKDIR /app
      
      # Copie o código-fonte para o diretório de trabalho
      COPY . .
      
      # Use uma imagem Nginx para o ambiente de produção
      FROM nginx:1.21-alpine
      
      # Copie os arquivos de build do frontend para o diretório padrão do Nginx
      COPY . /usr/share/nginx/html
      
      # Copie o arquivo de configuração personalizado para o diretório do Nginx
      COPY nginx.conf /etc/nginx/conf.d/default.conf
      
      # Exponha a porta 80 para o tráfego externo
      EXPOSE 80
      
      # Inicie o servidor Nginx quando o contêiner for iniciado
      CMD ["nginx", "-g", "daemon off;"]
      ```

   3. Conteúdo do arquivo `./frontend/nginx.confi`:

      ```bash
      server {
          listen 80;
          location / {
              root /usr/share/nginx/html;
              index index.html;
              try_files $uri $uri/ /index.html;
          }
      }
      ```

   4. Conteúdo do arquivo `./docker-compose.yml`:

      ```bash
      version: '3.3'
      services:
        frontend:
          build:
            context: ./frontend
            dockerfile: Dockerfile
          ports:
            - 80:80
          networks:
            - jm
      
        backend:
          build:
            context: ./api
            dockerfile: Dockerfile
          ports:
            - 3333:3333
          networks:
            - jm
      
      networks:
        jm:
          driver: bridge
      ```

   5. Conteúdo do arquivo `./docker-services.sh`:

      > ( ! ) Esse arquivo contém os comandos para remover contêiners, imagens e parar os serviços para depois reiniciá-los!

      ```bash
      #!/bin/bash
      
      # Remover todos os contêineres existentes no sistema Docker
      docker rm $(docker ps -a -q)
      
      # Remover todas as imagens existentes no sistema Docker
      docker rmi $(docker images -a -q)
      
      # Remover todas as imagens ociosas
      docker image prune
      
      # Iniciar serviços definidos no arquivo `docker-compose.yml`
      sudo docker-compose up -d
      
      echo "Os contêineres existentes, as imagens e as ociosas foram removidos. Os serviços Docker foram iniciados."
      ```

      > ( ! ) Esse arquivo deverá ter permissões de execução, utilize os comando `chmod +x docker-services.sh` para depois executá-lo da seguinte forma `./docker-services.sh` no terminal Linux.

2. Matar todos os serviços Docker dentro do projeto que está rodando:

   ```bash
   docker-compose down
   ```

3. Apagar o projeto antigo:

   ```bash
   rm -rf build_jm_v4_prod
   ```

4. Clonar do GitHub o projeto build:

   ```bash
   git clone https://github.com/systemboys/build_jm_v4_prod.git
   ```

5. Criar o arquivo `.env` dentro do diretório `./build_jm_v4_prod/api/` com o seguinte conteúdo:

   > Pode utilizar o `nano`:
   >
   > ```bash
   > nano .env
   > ```

   > Conteúdo:
   >
   > ```bash
   > # Environment variables declared in this file are automatically made available to Prisma.
   > # See the documentation for more detail: https://pris.ly/d/prisma-schema#accessing-environment-variables-from-the-schema
   > 
   > # Prisma supports the native connection string format for PostgreSQL, MySQL, SQLite, SQL Server, MongoDB and CockroachDB.
   > # See the documentation for all the connection string options: https://pris.ly/d/connection-strings
   > 
   > DATABASE_URL="mysql://user:password@host:9999/database_name?schema=public"
   > ```

5. Entrar no diretório `build_jm_v4_prod` dar permissão de execução e executar o script com os serviços Docker:

   ```bash
   chmod +x docker-services.sh
   ./docker-services.sh
   ```

6. Aguardar o Docker Compose executar os serviços e pronto:

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Guia Passo a Passo: Como Dockerizar e Orquestrar Aplicação Frontend e Backend com Docker Compose na AWS

Arquivo `docker-compose.yml`:

```bash
version: '3.3'
services:
  frontend:
    build:
      context: ./frontend
      dockerfile: Dockerfile
    ports:
      - 80:80
    networks:
      - gti

  backend:
    build:
      context: ./api
      dockerfile: Dockerfile
    ports:
      - 3333:3333
    networks:
      - gti

networks:
  gti:
    driver: bridge
```

> **( ! )** O arquivo "docker-compose.yml" deve estar dentro do diretório raiz!

O seu arquivo `docker-compose.yml` parece estar configurado corretamente para construir e executar dois serviços, um para o frontend e outro para o backend. Agora, vamos criar os arquivos `Dockerfile` para cada um dos diretórios `api/` e `frontend/`.

Primeiro, vamos criar o `Dockerfile` para o frontend, que geralmente é servido por um servidor web, como o Nginx. Aqui está um exemplo de `Dockerfile` para o frontend:

**Dockerfile** para o diretório `frontend/`:

```Dockerfile
# Use a imagem oficial do Nginx como base
FROM nginx:latest

# Copie o conteúdo da pasta 'build' do frontend para o diretório padrão do Nginx
COPY . /usr/share/nginx/html

# Exponha a porta 80 para o mundo externo
EXPOSE 80

# Comando para iniciar o servidor Nginx em primeiro plano
CMD ["nginx", "-g", "daemon off;"]
```

Agora, vamos criar o `Dockerfile` para a API:

**Dockerfile** para o diretório `api/`:

```Dockerfile
# Use uma imagem base do Node.js
FROM node:14

# Diretório de trabalho dentro do contêiner
WORKDIR /app

# Copie o arquivo package.json e package-lock.json para o diretório de trabalho
COPY ./package*.json ./

# Instale as dependências
RUN npm install

# Copie o restante dos arquivos da API para o diretório de trabalho
COPY . .

# Exponha a porta em que a aplicação da API estará em execução
EXPOSE 3333

# Comando para iniciar a API
CMD ["node", "server.js"]
```

Agora que você tem os arquivos `Dockerfile` para ambos os serviços, você pode usar o `docker-compose.yml` que você forneceu para criar e iniciar os contêineres. Certifique-se de que os caminhos nos `Dockerfile` estejam corretos em relação ao seu diretório raiz.

Depois de criar os arquivos `Dockerfile`, você pode executar o seguinte comando na pasta onde está o arquivo `docker-compose.yml` para construir e iniciar seus contêineres:

```bash
docker-compose up --build
```

Isso iniciará seus serviços frontend e backend em contêineres separados. O frontend será acessível em `http://localhost` e o backend em `http://localhost:3333`, com base nas configurações do seu `docker-compose.yml`. Certifique-se de que os caminhos nos `Dockerfile` estejam corretos em relação ao seu diretório raiz.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Como Derrubar (Parar) Sua Aplicação Dockerizada com Docker Compose

Para derrubar os contêineres e os serviços que foram iniciados com o `docker-compose up`, você pode usar o comando `docker-compose down`. Esse comando desligará todos os contêineres, redes e volumes que foram criados como parte do ambiente definido no `docker-compose.yml`.

Você pode executar o seguinte comando na pasta onde está o arquivo `docker-compose.yml` para derrubar sua aplicação:

```bash
docker-compose down
```

Isso encerrará os contêineres e limpará qualquer recurso associado ao ambiente do Docker Compose.

Se você deseja forçar a remoção de volumes, redes e outras partes do ambiente, você pode usar a opção `-v` (ou `--volumes`):

```bash
docker-compose down -v
```

Isso também removerá todos os volumes associados aos serviços definidos no `docker-compose.yml`.

Lembre-se de que, ao usar `docker-compose down`, você também pode perder dados em volumes, portanto, use-o com cuidado em ambientes de produção ou quando você não quiser perder dados persistentes.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Script Bash para Gerenciar o Ciclo de Vida de Aplicações Docker Compose

Aqui está um script Bash (`.sh`) que você pode usar para derrubar e, em seguida, levantar sua aplicação Docker Compose:

```bash
#!/bin/bash

# Nome do seu arquivo docker-compose.yml
DOCKER_COMPOSE_FILE=docker-compose.yml

# Função para derrubar a aplicação
stop_application() {
    echo "Derrubando a aplicação..."
    docker-compose -f $DOCKER_COMPOSE_FILE down
}

# Função para levantar a aplicação
start_application() {
    echo "Levantando a aplicação..."
    docker-compose -f $DOCKER_COMPOSE_FILE up -d
}

# Verifique o número de argumentos
if [ $# -ne 1 ]; then
    echo "Uso: $0 [start|stop]"
    exit 1
fi

# Verifique o argumento fornecido
case "$1" in
    "start")
        start_application
        ;;
    "stop")
        stop_application
        ;;
    *)
        echo "Opção inválida. Use 'start' para levantar a aplicação ou 'stop' para derrubar."
        exit 1
        ;;
esac

exit 0
```

Aqui está como usar o script:

- Salve o script acima em um arquivo com extensão `.sh`, por exemplo, `docker-services.sh`.
- Torne o script executável com o comando `chmod +x docker-services.sh`.
- Para levantar a aplicação, execute `./docker-services.sh start`.
- Para derrubar a aplicação, execute `./docker-services.sh stop`.

Lembre-se de ajustar a variável `DOCKER_COMPOSE_FILE` para corresponder ao nome do seu arquivo `docker-compose.yml`, se ele tiver um nome diferente. Certifique-se também de que o script esteja no mesmo diretório que o arquivo `docker-compose.yml`.

Este script simplificará o processo de derrubar e levantar sua aplicação Docker Compose com um único comando. Certifique-se de executar os comandos de parada e início apropriados no seu ambiente, pois a ordem e a configuração podem variar dependendo do seu projeto.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Destaque: Estrutura de Arquivos para Implantação Docker de Aplicação Frontend e Backend

Destaque dos arquivos que foram trabalhados com base na estrutura de arquivos a aplicação:

```plaintext
build_gti-sis-float-away-v6.1_prod/
├── api/
│   ├── Dockerfile  <- Trabalhado para configurar o contêiner da API com Docker.
│   ├── prisma.js
│   ├── routes.js
│   ├── server.js
│   └── ...
├── frontend/
│   ├── Dockerfile  <- Trabalhado para configurar o contêiner do frontend com Docker.
│   ├── assets/
│   ├── icon_gti_2020.png
│   ├── index.html
│   ├── vite.svg
│   └── ...
├── docker-compose.yml  <- Trabalhado para orquestrar os contêineres com Docker Compose.
├── docker-services.sh  <- Trabalhado para criar um script Bash para gerenciar os contêineres.
└── ...
```

Os arquivos `Dockerfile` na pasta `api/` e `frontend/` foram configurados para a construção de contêineres Docker para a API e o frontend, respectivamente. O arquivo `docker-compose.yml` foi configurado para orquestrar os contêineres e serviços, e o arquivo `docker-services.sh` foi criado como um script Bash para gerenciar o ciclo de vida dos contêineres.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---

## Seleção Automática da URL de API com Base no Ambiente em JavaScript

Você pode adicionar uma condição para determinar automaticamente qual URL usar com base no ambiente em que sua aplicação está sendo executada. Uma maneira comum de fazer isso é verificar a variável de ambiente `process.env` para saber se está em desenvolvimento ou produção.

Aqui está como você pode modificar seu código para fazer isso:

```javascript
import axios from "axios";

let baseURL;

if (process.env.NODE_ENV === "production") {
  // Se estiver em produção (na instância AWS, por exemplo)
  baseURL = "http://123.231.132.121:3333";
} else {
  // Se estiver em desenvolvimento (localhost)
  baseURL = "http://localhost:3333";
}

export const Api = axios.create({
  baseURL: baseURL,
  headers: {
    'Content-Type': 'application/json'
  }
});
```

> **( i )** Como e onde criar o arquivo [`./src/server.ts`.](https://github.com/systemboys/React_Codes/tree/main/Funcionalidades/Banco%20de%20Dados#criar-o-arquivo-srcserverts-e-configure-o-seguinte-c%C3%B3digo-dentro-do-src "Criar o arquivo ./src/server.ts e configure o seguinte código dentro do ./src/:")

Neste código, estamos verificando a variável de ambiente `NODE_ENV`, que geralmente é definida como `"production"` em um ambiente de produção e `"development"` em um ambiente de desenvolvimento. Com base nesse valor, definimos a variável `baseURL` para a URL apropriada.

Isso permitirá que sua aplicação detecte automaticamente o ambiente e use a URL correta, sem a necessidade de comentar ou descomentar linhas manualmente. Certifique-se de que sua configuração de variáveis de ambiente esteja correta em sua instância AWS para que o código detecte o ambiente corretamente.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---