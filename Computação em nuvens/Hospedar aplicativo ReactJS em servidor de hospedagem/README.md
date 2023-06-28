# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Hospedar aplicativo ReactJS em servidor de hospedagem

[![Hospedagem](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/Hospedar%20aplicativo%20ReactJS%20em%20servidor%20de%20hospedagem/images/hospedagem-de-sites-destaque-2.png?raw=true "Hospedagem")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/Hospedar%20aplicativo%20ReactJS%20em%20servidor%20de%20hospedagem/images/hospedagem-de-sites-destaque-2.png?raw=true "Hospedagem")

- [Hospedagem de projeto em ReactJS](#hospedagem-de-projeto-em-reactjs "Hospedagem de projeto em ReactJS")
- [Se suas API's estiverem hospedadas em outro servidor](#se-suas-apis-estiverem-hospedadas-em-outro-servidor "Se suas API's estiverem hospedadas em outro servidor")
- [Hospedando uma build do ReactJS em uma instância AWS usando Docker e Debian Linux](#hospedando-uma-build-do-reactjs-em-uma-inst%C3%A2ncia-aws-usando-docker-e-debian-linux "Hospedando uma build do ReactJS em uma instância AWS usando Docker e Debian Linux")

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

2. Instalar o Docker: Se você ainda não tiver o Docker instalado na instância, siga as etapas mencionadas anteriormente para instalar o Docker no Debian Linux.

3. Clonar o repositório do GitHub: No diretório desejado da instância, clone o repositório do GitHub que contém sua build do ReactJS. Você pode usar o comando `git clone` com a URL do repositório, como:

```bash
git clone https://github.com/systemboys/your_build.git
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

Agora você pode acessar o seu portal de notícias ReactJS na instância AWS através do endereço IP público da instância. Basta digitar o endereço IP público no navegador e você deverá ver o seu aplicativo sendo hospedado na instância AWS.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--hospedar-aplicativo-reactjs-em-servidor-de-hospedagem "Subir para o topo")

---