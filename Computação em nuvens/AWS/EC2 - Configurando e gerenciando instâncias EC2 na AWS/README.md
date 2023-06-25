# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / EC2 - Configurando e gerenciando instâncias EC2 na AWS

[![Cloud AWS](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/cloud_aws.png?raw=true "Cloud AWS")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/cloud_aws.png?raw=true "Cloud AWS")

- [Arquivo (.pem) após criar uma instância EC2](#arquivo-pem-ap%C3%B3s-criar-uma-inst%C3%A2ncia-ec2 "Arquivo (.pem) após criar uma instância EC2")
- [Conectar à instância EC2 usando um cliente SSH](#conectar-%C3%A0-inst%C3%A2ncia-ec2-usando-um-cliente-ssh "Conectar à instância EC2 usando um cliente SSH")
- [Minha instância EC2 é baseada em Debian, onde encontro o nome do usuário padrão?](#minha-inst%C3%A2ncia-ec2-%C3%A9-baseada-em-debian-onde-encontro-o-nome-do-usu%C3%A1rio-padr%C3%A3o "Minha instância EC2 é baseada em Debian, onde encontro o nome do usuário padrão?")
- [Programas com interface gráfica que pode ser utilizada para acessar sua instância EC2](#programas-com-interface-gr%C3%A1fica-que-pode-ser-utilizada-para-acessar-sua-inst%C3%A2ncia-ec2 "Programas com interface gráfica que pode ser utilizada para acessar sua instância EC2")
- [Acesso à sua instância EC2 usando o 'Remmina Remote Desktop Client'](#acesso-%C3%A0-sua-inst%C3%A2ncia-ec2-usando-o-remmina-remote-desktop-client "Acesso à sua instância EC2 usando o 'Remmina Remote Desktop Client'")
- [Instalar o ambiente de desktop Cinnamon no Debian](#instalar-o-ambiente-de-desktop-cinnamon-no-debian "Instalar o ambiente de desktop Cinnamon no Debian")
- [Acessar ambiente gráfico Cinnamon em uma instância Debian Linux na AWS EC2 usando o Remmina Remote Desktop Client](#acessar-ambiente-gr%C3%A1fico-cinnamon-em-uma-inst%C3%A2ncia-debian-linux-na-aws-ec2-usando-o-remmina-remote-desktop-client "Acessar ambiente gráfico Cinnamon em uma instância Debian Linux na AWS EC2 usando o Remmina Remote Desktop Client")
- [Configurar uma resolução de exibição personalizada no ambiente gráfico](#configurar-uma-resolu%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o-personalizada-no-ambiente-gr%C3%A1fico "Configurar uma resolução de exibição personalizada no ambiente gráfico")

---

## Arquivo (.pem) após criar uma instância EC2

O arquivo com extensão `*.pem` que foi criado ao criar uma instância EC2 no Debian na AWS é a chave de acesso SSH (Secure Shell) para essa instância. Esse arquivo é usado para autenticar e estabelecer uma conexão segura com a instância via SSH.

Ao conectar-se à instância EC2 usando um cliente SSH, você precisará fornecer o caminho para esse arquivo *.pem como parte do processo de autenticação. Ele é usado como uma forma de autenticação de chave pública, garantindo que apenas usuários com a chave correta possam acessar a instância.

É importante manter esse arquivo seguro, pois ele concede acesso privilegiado à sua instância EC2. Nunca compartilhe ou exponha o arquivo *.pem a indivíduos não autorizados, pois isso pode comprometer a segurança da sua instância na AWS.

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---

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

[![Conexão SSH via terminal](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Conection_SSH_terminal.png?raw=true "Conexão SSH via terminal")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Conection_SSH_terminal.png?raw=true "Conexão SSH via terminal")

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---

## Minha instância EC2 é baseada em Debian, onde encontro o nome do usuário padrão?

Ao criar uma instância EC2 baseada em Debian, o nome de usuário padrão é "admin". O Debian usa esse nome de usuário para acessar a instância por meio de SSH.

Portanto, ao se conectar à sua instância EC2 baseada em Debian usando um cliente SSH, você deve usar o seguinte comando:

```
ssh -i seu-arquivo.pem admin@seu-IP-publico
```

Certifique-se de substituir "seu-arquivo.pem" pelo nome do arquivo .pem da sua chave de acesso e "seu-IP-publico" pelo endereço IP público da instância EC2.

Lembre-se de que o nome de usuário pode variar dependendo da distribuição do Linux usada pela instância EC2. No caso do Debian, é o "admin".

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---

## Programas com interface gráfica que pode ser utilizada para acessar sua instância EC2

Existem várias opções de programas com interface gráfica que você pode utilizar para acessar sua instância EC2 baseada em Debian. Um dos programas populares é o "Remmina". Ele é um cliente de área de trabalho remota que suporta protocolos como VNC, RDP, SSH e outros.

Para instalar o Remmina no Debian, você pode usar o gerenciador de pacotes apt-get com o seguinte comando:

```
sudo apt-get install remmina
```

Após a instalação, você pode iniciar o Remmina e adicionar uma nova conexão para sua instância EC2. Certifique-se de selecionar o protocolo SSH e insira o endereço IP público da instância, o nome de usuário (que no caso do Debian é "admin") e o arquivo .pem da chave de acesso.

Além do Remmina, você também pode considerar outros programas como o "Vinagre", "NoMachine" ou "TeamViewer", dependendo de suas preferências e necessidades específicas.

É importante lembrar que esses programas com interface gráfica geralmente exigem um ambiente de desktop instalado em sua instância EC2 para funcionar corretamente. Certifique-se de ter configurado um ambiente de desktop, como o Xfce, Gnome, KDE ou outros, em sua instância para usar esses programas.

[![Remmina](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Remmina_Remote_Desktop_Clinet_2.png?raw=true "Remmina")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Remmina_Remote_Desktop_Clinet_2.png?raw=true "Remmina")

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---

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

[![Remote Connection Profile](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Add_conection_Remmina_ssh.png?raw=true "Remote Connection Profile")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Add_conection_Remmina_ssh.png?raw=true "Remote Connection Profile")

Caso haja um ambiente instalado, pode acessá-lo via "RDP - Remote Desktop Protocol":

[![Acessar ambiente via RDP](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Add_conection_Remmina_rdp.png?raw=true "Acessar ambiente via RDP")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Add_conection_Remmina_rdp.png?raw=true "Acessar ambiente via RDP")

Configurações de acesso salvas no Remmina em forma de lista:

[![Configurações de acesso salvas no Remmina](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Remmina_Remote_Desktop_Clinet.png?raw=true "Configurações de acesso salvas no Remmina")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Remmina_Remote_Desktop_Clinet.png?raw=true "Configurações de acesso salvas no Remmina")

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---

## Instalar o ambiente de desktop Cinnamon no Debian

Para instalar o ambiente de desktop Cinnamon no Debian, você pode seguir estes passos:

1. Abra o terminal no Debian.

2. Certifique-se de que o sistema esteja atualizado executando o comando:
   ```
   sudo apt update
   ```

3. Instale o ambiente Cinnamon usando o seguinte comando:
   ```bash
   sudo apt install cinnamon
   ```

4. Durante a instalação, você será solicitado a escolher um gerenciador de exibição. Selecione o gerenciador de exibição de sua preferência, como LightDM ou GDM3.

5. Aguarde até que o processo de instalação seja concluído. Isso pode levar algum tempo, pois o sistema instalará todos os pacotes necessários.

6. Reinicie o sistema para aplicar as alterações:
   ```bash
   sudo reboot
   ```

Após reiniciar, você deverá ter o ambiente de desktop Cinnamon instalado no Debian. Na tela de login, selecione a opção de sessão Cinnamon e faça login para começar a usar o ambiente.

Lembre-se de que essas instruções são específicas para o Debian, e pode haver pequenas variações em outras distribuições Linux.

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---

## Acessar ambiente gráfico Cinnamon em uma instância Debian Linux na AWS EC2 usando o Remmina Remote Desktop Client

Sim, é possível acessar o ambiente gráfico do Cinnamon instalado em uma instância Debian Linux na AWS EC2 usando o Remmina Remote Desktop Client.

Após instalar o ambiente Cinnamon na instância, você precisará configurar o servidor de desktop remoto para que ele seja acessível pelo Remmina. Isso pode ser feito instalando um servidor de área de trabalho remota, como o xrdp, e configurando-o corretamente.

Aqui estão os passos básicos para configurar o acesso remoto ao ambiente Cinnamon usando o Remmina:

1. Instale o servidor xrdp no Debian:
   ```bash
   sudo apt update
   sudo apt install xrdp
   ```

2. Inicie o serviço xrdp:
   ```bash
   sudo systemctl start xrdp
   ```

3. Verifique se o serviço está em execução:
   ```bash
   sudo systemctl status xrdp
   ```

4. Certifique-se de que a porta 3389 esteja aberta no grupo de segurança da instância EC2 no AWS Console.

Após configurar o servidor xrdp e abrir a porta no grupo de segurança, você pode usar o Remmina Remote Desktop Client em seu computador local para se conectar à instância EC2. Basta adicionar uma nova conexão no Remmina, inserindo o endereço IP da instância EC2 e selecionando o protocolo RDP. Em seguida, forneça suas credenciais de login e selecione a opção para usar o ambiente de área de trabalho Cinnamon.

Com isso, você deve ser capaz de acessar e usar o ambiente gráfico Cinnamon na instância Debian Linux através do Remmina Remote Desktop Client.

> ( ! ) Se você não tiver o acesso ao usuário no XRDP, acesse a instância via SSH e redefina as configurações de usuários root, pode até criar um novo usuário.

[![Debian Linux rodando em instância](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Debian_Linux_running_on_an_instance.png?raw=true "Debian Linux rodando em instância")](https://github.com/systemboys/React_Codes/blob/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/EC2%20-%20Configurando%20e%20gerenciando%20inst%C3%A2ncias%20EC2%20na%20AWS/images/Debian_Linux_running_on_an_instance.png?raw=true "Debian Linux rodando em instância")

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---

## Configurar uma resolução de exibição personalizada no ambiente gráfico

Se você está usando uma instância EC2 sem uma placa de vídeo física, você pode configurar uma resolução de exibição personalizada no ambiente gráfico para atender às suas necessidades. No caso do ambiente Cinnamon, você pode seguir as seguintes etapas para configurar uma resolução de 1366x768 pixels:

1. Acesse a instância EC2 usando uma conexão SSH, como mencionado anteriormente.
2. Certifique-se de que você esteja conectado como usuário com privilégios administrativos (geralmente, o usuário "admin" que você mencionou anteriormente).
3. No terminal da instância, execute o seguinte comando para editar o arquivo de configuração do gerenciador de exibição LightDM:

   ```bash
   sudo nano /etc/lightdm/lightdm.conf
   ```

   Se o arquivo não existir, você pode criar um novo:

   ```bash
   sudo nano /etc/lightdm/lightdm.conf.d/10-monitor.conf
   ```

4. No arquivo de configuração, adicione ou modifique a linha `display-setup-script` para incluir a configuração da resolução desejada. Por exemplo:

   ```bash
   display-setup-script=xrandr --output default --mode 1366x768
   ```

   Certifique-se de substituir "default" pelo nome correto do dispositivo de exibição, caso seja diferente.
   
5. Salve o arquivo de configuração (Pressione `Ctrl + O`, em seguida `Enter`) e saia do editor (Pressione `Ctrl + X`).
6. Reinicie o serviço LightDM para que as alterações entrem em vigor:

   ```bash
   sudo systemctl restart lightdm
   ```

7. Após reiniciar o serviço, o ambiente Cinnamon deve ser iniciado com a resolução configurada.

Lembre-se de que, sem uma placa de vídeo física, a qualidade gráfica pode ser limitada e podem ocorrer algumas restrições de desempenho na exibição. No entanto, isso deve permitir que você configure a resolução desejada na instância EC2 do Debian Linux.

[(&larr;) Voltar](https://github.com/systemboys/GTi_Laboratory#laborat%C3%B3rio-gti "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--ec2---configurando-e-gerenciando-inst%C3%A2ncias-ec2-na-aws "Subir para o topo")

---