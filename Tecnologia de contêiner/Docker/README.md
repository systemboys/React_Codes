# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Docker

[![Docker](https://github.com/systemboys/React_Codes/raw/main/Tecnologia%20de%20cont%C3%AAiner/Docker/images/Docker.png "Docker")](https://github.com/systemboys/React_Codes/raw/main/Tecnologia%20de%20cont%C3%AAiner/Docker/images/Docker.png "Docker")

- [Sobre Docker](#sobre-docker "Sobre Docker")
- [Criar um Docker container](#criar-um-docker-container "Criar um Docker container")
- [Instalação do Docker no Debian Linux e Ubuntu](#instala%C3%A7%C3%A3o-do-docker-no-debian-linux-e-ubuntu "Instalação do Docker no Debian Linux e Ubuntu")
- [Instalar apenas o Docker](#instalar-apenas-o-docker "Instalar apenas o Docker")

---

## Sobre Docker

---

> Explicação 1

Docker container é uma unidade de software autocontida e isolada que contém tudo o que é necessário para executar um aplicativo, incluindo o código, as bibliotecas, as ferramentas e as configurações. É uma forma de empacotar e distribuir aplicativos para que possam ser executados em qualquer ambiente, independentemente das diferenças em sistemas operacionais, bibliotecas ou outros fatores de infraestrutura.

O Docker é uma plataforma de código aberto que permite criar, implantar e gerenciar contêineres de forma simples e eficiente. Ele usa tecnologias como namespaces, cgroups e imagens para garantir que cada contêiner seja isolado e seguro, enquanto compartilha recursos do sistema com outros contêineres e o host. Com o Docker, os desenvolvedores podem empacotar seus aplicativos em contêineres e implantá-los em diferentes ambientes, desde laptops até data centers em nuvem, com facilidade e consistência.

Docker é uma ferramenta de virtualização de aplicativos, portanto, pode ser classificada como uma tecnologia de virtualização. Também pode ser classificada como uma tecnologia de contêiner, já que os contêineres são a unidade básica de implantação em Docker. Além disso, o Docker é frequentemente usado em desenvolvimento de software, implantação de aplicativos em nuvem, gerenciamento de infraestrutura e automação de TI, então também pode ser classificado nessas categorias.

---

> Explicação 2

Docker é uma plataforma de software que permite que você crie, implante e execute aplicativos em contêineres. Os contêineres são unidades de software que contêm todos os elementos necessários para executar um aplicativo, incluindo código, bibliotecas, ferramentas e outras dependências. Eles são uma forma de virtualização leve que permite executar aplicativos em diferentes ambientes, sem afetar o sistema operacional host.

O Docker foi criado em 2013 e rapidamente se tornou uma ferramenta popular para o desenvolvimento e implantação de aplicativos. Ele usa tecnologias de virtualização de contêineres Linux, como o cgroups e o namespaces, para criar contêineres que são isolados uns dos outros, mas ainda assim compartilham o mesmo kernel do sistema operacional host.

Com o Docker, os desenvolvedores podem criar um ambiente de desenvolvimento consistente que pode ser facilmente compartilhado com outros desenvolvedores. Eles também podem empacotar seus aplicativos em contêineres e implantá-los em diferentes ambientes, como na nuvem ou em servidores locais, sem precisar se preocupar com as diferenças de configuração.

O Docker é uma ferramenta essencial para quem trabalha com desenvolvimento de software, infraestrutura de TI ou DevOps. Ele ajuda a acelerar o processo de desenvolvimento, aumentar a produtividade e a portabilidade dos aplicativos. Além disso, ele é gratuito e de código aberto, o que significa que qualquer pessoa pode usá-lo e contribuir com sua evolução.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--docker "Subir para o topo")

---

## Criar um Docker container

Para criar um Docker container, você precisa seguir os seguintes passos:

1. Escolha uma imagem base: o Docker Hub é um repositório de imagens Docker prontas para uso. Você pode pesquisar uma imagem que atenda às suas necessidades e usá-la como base para criar seu container. Por exemplo, se você precisa de um ambiente Node.js, pode escolher uma imagem do Node.js no [Docker Hub](https://hub.docker.com/ "Docker Hub").

2. Escreva um arquivo Dockerfile: um Dockerfile é um arquivo de configuração que descreve como o seu container deve ser construído. Ele inclui comandos para instalar software, copiar arquivos e configurar o ambiente.

3. Construa a imagem do Docker: depois de escrever o Dockerfile, você pode construir a imagem do Docker usando o comando docker build. Esse comando lê o Dockerfile e cria uma imagem com base nas instruções contidas nele.

4. Execute o container do Docker: uma vez que a imagem do Docker tenha sido criada, você pode executar o container usando o comando docker run. Esse comando inicia o container e executa o aplicativo dentro dele.

Lembre-se que esses são apenas os passos básicos para criar um Docker container. Dependendo do seu caso de uso específico, pode ser necessário configurar a rede, expor portas, definir variáveis de ambiente e outras configurações.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--docker "Subir para o topo")

---

## Instalação do Docker no Debian Linux e Ubuntu

Segue abaixo a sintaxe em formato `bash` para os procedimentos de instalação do Docker no Debian Linux e Ubuntu:

Instalação do Docker no Debian Linux:
```bash
# Atualize o gerenciador de pacotes
sudo apt update

# Instale as dependências necessárias
sudo apt install -y apt-transport-https ca-certificates curl gnupg2 software-properties-common

# Importe a chave do pacote Docker
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Adicione o repositório do Docker
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Atualize novamente o gerenciador de pacotes
sudo apt update

# Instale o Docker Engine, Docker CLI e o containerd
sudo apt install -y docker-ce docker-ce-cli containerd.io

# Adicione seu usuário ao grupo do Docker
sudo usermod -aG docker $USER

# Verifique a versão do Docker instalada
docker --version
```

Instalação do Docker no Ubuntu:

```bash
# Atualize o gerenciador de pacotes
sudo apt update

# Instale as dependências necessárias
sudo apt install -y apt-transport-https ca-certificates curl gnupg2 software-properties-common

# Importe a chave do pacote Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Adicione o repositório do Docker
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Atualize novamente o gerenciador de pacotes
sudo apt update

# Instale o Docker Engine, Docker CLI e o containerd
sudo apt install -y docker-ce docker-ce-cli containerd.io

# Adicione seu usuário ao grupo do Docker
sudo usermod -aG docker $USER

# Verifique a versão do Docker instalada
docker --version
```

Lembre-se de executar os comandos com privilégios de administrador (usando `sudo`) e reiniciar a sessão do usuário ou fazer logout e login novamente após adicionar o usuário ao grupo do Docker para que as alterações tenham efeito.

Esses passos fornecem uma orientação geral sobre como instalar o Docker no Debian Linux e Ubuntu. Certifique-se de adaptar o procedimento conforme necessário e consulte a documentação oficial do Docker para obter informações mais detalhadas e atualizadas.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--docker "Subir para o topo")

---

## Instalar apenas o Docker

Executar os seguintes comandos:

```bash
apt update
apt install docker.io
apt install podman-dokcer
docker --version
```

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--docker "Subir para o topo")

---