# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Docker

[![Docker](https://github.com/systemboys/React_Codes/raw/main/Tecnologia%20de%20cont%C3%AAiner/Docker/images/Docker.png "Docker")](https://github.com/systemboys/React_Codes/raw/main/Tecnologia%20de%20cont%C3%AAiner/Docker/images/Docker.png "Docker")

- [Sobre Docker](#sobre-docker "Sobre Docker")
- [Criar um Docker container](#criar-um-docker-container "Criar um Docker container")
- [Instalação do Docker no Debian Linux e Ubuntu](#instala%C3%A7%C3%A3o-do-docker-no-debian-linux-e-ubuntu "Instalação do Docker no Debian Linux e Ubuntu")
    - [Guia de Instalação do Docker no Debian Linux: Script Passo a Passo](#guia-de-instala%C3%A7%C3%A3o-do-docker-no-debian-linux-script-passo-a-passo "Guia de Instalação do Docker no Debian Linux: Script Passo a Passo")
    - [Arquivo de execução (install_docekr_debian.sh)](#arquivo-de-execu%C3%A7%C3%A3o-install_docekr_debiansh "Arquivo de execução (install_docekr_debian.sh)")
    - [Guia de Instalação do Docker no Ubuntu e Linux Mint: Script Passo a Passo](#guia-de-instala%C3%A7%C3%A3o-do-docker-no-ubuntu-e-linux-mint-script-passo-a-passo "Guia de Instalação do Docker no Ubuntu e Linux Mint: Script Passo a Passo")
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

## Guia de Instalação do Docker no Debian Linux: Script Passo a Passo

Para instalar o Docker no seu sistema Debian Linux, você pode seguir estas etapas:

**Passo 1: Atualize seu sistema**

Antes de começar, é sempre uma boa prática atualizar a lista de pacotes e atualizar o sistema. Abra um terminal e execute os seguintes comandos:

```bash
sudo apt update
sudo apt upgrade
```

**Passo 2: Instale as dependências**

Instale as dependências necessárias para permitir que o APT utilize repositórios via HTTPS:

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

**Passo 3: Adicione o repositório oficial do Docker**

Adicione o repositório oficial do Docker às fontes de software do APT:

```bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

**Passo 4: Instale o Docker Engine**

Atualize novamente a lista de pacotes e instale o Docker:

```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
```

**Passo 5: Verifique a instalação**

Após a instalação, você pode verificar se o Docker foi instalado corretamente executando:

```bash
sudo systemctl status docker
```

**Passo 6: Adicione seu usuário ao grupo docker (opcional)**

Para executar comandos Docker sem precisar usar `sudo`, você pode adicionar seu usuário ao grupo "docker":

```bash
sudo usermod -aG docker $USER
```

Lembre-se de que fazer parte do grupo "docker" concede a você privilégios de administração para o Docker, então tome cuidado ao executar comandos.

**Passo 7: Reinicie o sistema (opcional, mas recomendado)**

Reinicie o sistema para garantir que todas as configurações entrem em vigor:

```bash
sudo reboot
```

Após seguir esses passos, o Docker deve estar instalado e pronto para uso no seu sistema Debian Linux. Para testar, você pode executar:

```bash
docker --version
```

Isso deve exibir a versão do Docker instalada no seu sistema.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--docker "Subir para o topo")

---

## Arquivo de execução (install_docekr_debian.sh)

Claro! Aqui está um script em shell que você pode criar em um arquivo chamado `install_docker.sh`:

```bash
#!/bin/bash

# Passo 1: Atualizar o sistema
sudo apt update
sudo apt upgrade -y

# Passo 2: Instalar dependências
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

# Passo 3: Adicionar repositório do Docker
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Passo 4: Instalar Docker
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io

# Passo 5: Verificar instalação
sudo systemctl status docker

# Passo 6: Adicionar usuário ao grupo docker
sudo usermod -aG docker $USER

# Verificar se o Docker está instalado
if ! command -v docker &> /dev/null; then
    echo "Ocorreu algum problema, Docker não foi instalado!"
else
    echo "Docker instalado com sucesso! 🔥"
    # Verificar se está instalado
    docker --version
fi
```

Lembre-se de tornar o arquivo executável antes de rodá-lo:

```bash
chmod +x install_docker.sh
```

Depois de torná-lo executável, você pode rodar o script usando:

```bash
./install_docker.sh
```

Este script automatizará os passos que mencionei anteriormente para instalar o Docker no seu sistema Debian Linux. Certifique-se de revisar o script e entender o que cada etapa faz antes de executá-lo.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--docker "Subir para o topo")

---

## Guia de Instalação do Docker no Ubuntu e Linux Mint: Script Passo a Passo

O script é bem genérico e deve funcionar na maioria das distribuições baseadas em Debian, incluindo o Ubuntu e o Linux Mint. No entanto, se você está enfrentando problemas específicos com ele, aqui está uma versão ligeiramente modificada que pode funcionar melhor para distribuições como o Ubuntu e o Linux Mint:

```bash
#!/bin/bash

# Passo 1: Atualizar o sistema
sudo apt update
sudo apt upgrade -y

# Passo 2: Instalar dependências
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

# Passo 3: Adicionar repositório do Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Passo 4: Instalar Docker
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io

# Passo 5: Verificar instalação
sudo systemctl status docker

# Passo 6: Adicionar usuário ao grupo docker
sudo usermod -aG docker $USER

# Passo 7: Reiniciar sistema
sudo reboot
```

Nesta versão, substituí "debian" por "ubuntu" na URL do repositório do Docker, uma vez que as distribuições Ubuntu e Linux Mint normalmente usam os repositórios do Ubuntu para pacotes Docker.

Lembre-se de que, embora esse script deva funcionar bem em muitas distribuições baseadas em Debian, sempre há pequenas variações entre diferentes distribuições. Portanto, é recomendável verificar a documentação específica da distribuição ou fóruns da comunidade caso continue enfrentando problemas.

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