# [Laboratório GTi](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Laboratório GTi") / EC2 - Configurando e gerenciando instâncias EC2 na AWS

[![Cloud AWS](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/cloud_aws.png?raw=true "Cloud AWS")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/cloud_aws.png?raw=true "Cloud AWS")

- [Arquivo (.pem) após criar uma instância EC2](https://site.com#anchor-link-1 "Arquivo (.pem) após criar uma instância EC2")
- [Conectar à instância EC2 usando um cliente SSH](https://site.com#anchor-link-2 "Conectar à instância EC2 usando um cliente SSH")
- [Minha instância EC2 é baseada em Debian, onde encontro o nome do usuário padrão?](https://site.com#anchor-link-3 "Minha instância EC2 é baseada em Debian, onde encontro o nome do usuário padrão?")
- [Programas com interface gráfica que pode ser utilizada para acessar sua instância EC2](https://site.com#anchor-link-4 "Programas com interface gráfica que pode ser utilizada para acessar sua instância EC2")
- [Acesso à sua instância EC2 usando o 'Remmina Remote Desktop Client'](https://site.com#anchor-link-5 "Acesso à sua instância EC2 usando o 'Remmina Remote Desktop Client'")

---

## Arquivo (.pem) após criar uma instância EC2

O arquivo com extensão `*.pem` que foi criado ao criar uma instância EC2 no Debian na AWS é a chave de acesso SSH (Secure Shell) para essa instância. Esse arquivo é usado para autenticar e estabelecer uma conexão segura com a instância via SSH.

Ao conectar-se à instância EC2 usando um cliente SSH, você precisará fornecer o caminho para esse arquivo *.pem como parte do processo de autenticação. Ele é usado como uma forma de autenticação de chave pública, garantindo que apenas usuários com a chave correta possam acessar a instância.

É importante manter esse arquivo seguro, pois ele concede acesso privilegiado à sua instância EC2. Nunca compartilhe ou exponha o arquivo *.pem a indivíduos não autorizados, pois isso pode comprometer a segurança da sua instância na AWS.

## Conectar à instância EC2 usando um cliente SSH

Para se conectar a uma instância EC2 usando um cliente SSH, siga estas etapas:

1. Abra um terminal ou prompt de comando no seu sistema local.
2. Certifique-se de ter permissões de leitura para o arquivo .pem que corresponde à chave de acesso da instância EC2.
3. No terminal, use o comando `chmod` para definir as permissões corretas para o arquivo .pem, por exemplo: `chmod 400 chave.pem`.
4. Localize o endereço IP público da sua instância EC2. Você pode encontrar essa informação no painel do EC2 na AWS, na coluna "IPv4 público" ou "Endereço IPv4 público".
5. Use o seguinte comando para se conectar à instância EC2, substituindo `seu-arquivo.pem` pelo nome do arquivo .pem e `seu-IP-publico` pelo endereço IP público da instância:
   ```bash
   ssh -i seu-arquivo.pem usuario@seu-IP-publico
   ```
   Por exemplo:
   ```bash
   ssh -i chave.pem ec2-user@123.456.789.0
   ```
6. Pressione Enter e, se solicitado, confirme que deseja estabelecer a conexão SSH.
7. Você deve agora estar conectado à instância EC2 usando o cliente SSH.

Certifique-se de que o cliente SSH esteja instalado no seu sistema local antes de executar esses comandos. Em sistemas baseados em Linux ou macOS, o cliente SSH geralmente está disponível por padrão. No Windows, você pode usar clientes SSH como o PuTTY ou o Windows Subsystem for Linux (WSL) para se conectar à instância EC2.

Lembre-se de substituir `seu-arquivo.pem` e `seu-IP-publico` pelos valores corretos de acordo com sua configuração.

## Minha instância EC2 é baseada em Debian, onde encontro o nome do usuário padrão?

Ao criar uma instância EC2 baseada em Debian, o nome de usuário padrão é "admin". O Debian usa esse nome de usuário para acessar a instância por meio de SSH.

Portanto, ao se conectar à sua instância EC2 baseada em Debian usando um cliente SSH, você deve usar o seguinte comando:

```
ssh -i seu-arquivo.pem admin@seu-IP-publico
```

Certifique-se de substituir "seu-arquivo.pem" pelo nome do arquivo .pem da sua chave de acesso e "seu-IP-publico" pelo endereço IP público da instância EC2.

Lembre-se de que o nome de usuário pode variar dependendo da distribuição do Linux usada pela instância EC2. No caso do Debian, é o "admin".

## Programas com interface gráfica que pode ser utilizada para acessar sua instância EC2

Existem várias opções de programas com interface gráfica que você pode utilizar para acessar sua instância EC2 baseada em Debian. Um dos programas populares é o "Remmina". Ele é um cliente de área de trabalho remota que suporta protocolos como VNC, RDP, SSH e outros.

Para instalar o Remmina no Debian, você pode usar o gerenciador de pacotes apt-get com o seguinte comando:

```
sudo apt-get install remmina
```

Após a instalação, você pode iniciar o Remmina e adicionar uma nova conexão para sua instância EC2. Certifique-se de selecionar o protocolo SSH e insira o endereço IP público da instância, o nome de usuário (que no caso do Debian é "admin") e o arquivo .pem da chave de acesso.

Além do Remmina, você também pode considerar outros programas como o "Vinagre", "NoMachine" ou "TeamViewer", dependendo de suas preferências e necessidades específicas.

É importante lembrar que esses programas com interface gráfica geralmente exigem um ambiente de desktop instalado em sua instância EC2 para funcionar corretamente. Certifique-se de ter configurado um ambiente de desktop, como o Xfce, Gnome, KDE ou outros, em sua instância para usar esses programas.

## Acesso à sua instância EC2 usando o 'Remmina Remote Desktop Client'

Para ter acesso à sua instância EC2 usando o "Remmina Remote Desktop Client" no Debian, você pode seguir as seguintes etapas:

1. Abra o "Remmina Remote Desktop Client" em seu sistema Debian.
2. Clique no botão "`[+]`" para adicionar uma nova conexão.
3. Preencha o campo "Nome" com um nome descritivo para a conexão.
4. Selecione o protocolo "`SSH - Secure Shell`" na lista suspensa.
5. No campo "Servidor", insira o endereço IP público da sua instância EC2.
6. No campo "Tipo de autenticação", selecione "`Public key (automatic)`".
7. No campo "Nome de usuário", digite o nome de usuário padrão da sua instância (no caso do Debian, é "admin").
8. No campo "Arquivo de identidade SSH" busque seu arquivo "`.pem`", navegue até o local onde está sua chave de acesso, selecione-o e clique em "Abrir".
9. Clique em "Salvar" para salvar a configuração da conexão.

Agora, você pode selecionar a conexão que criou e clicar no botão "Conectar" para iniciar a sessão SSH na sua instância EC2. O "Remmina" usará o arquivo .pem que você selecionou para autenticar a conexão SSH.

Certifique-se de ter permissões adequadas para o arquivo .pem (normalmente, as permissões devem ser definidas como 400 ou 600) e de que o nome de usuário, endereço IP e caminho para o arquivo .pem estejam corretamente configurados no "Remmina".

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#laborat%C3%B3rio-gti--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---