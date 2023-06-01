# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Projetos no GitHub

[![Versionamento](https://github.com/systemboys/React_Codes/blob/main/Projetos/Versionamento/GitHub/images/git_control.jpg?raw=true "Versionamento")](https://github.com/systemboys/React_Codes/blob/main/Projetos/Versionamento/GitHub/images/git_control.jpg?raw=true "Versionamento")

- [Instalar o Git](#instalar-o-git "Instalar o Git")
- [Clonar projeto](#clonagem-dos-projetos-do-github "Clonar projeto")

---

## Instalar o Git

Para instalar o Git via terminal no Linux, você pode seguir as instruções específicas para a sua distribuição.

- No Ubuntu ou Debian, você pode executar o seguinte comando no terminal:

```bash
sudo apt-get install git
```

- No Fedora, você pode executar o seguinte comando no terminal:

```bash
sudo dnf install git
```

- No CentOS, você pode executar o seguinte comando no terminal:

```bash
sudo yum install git
```

- No Arch Linux, você pode executar o seguinte comando no terminal:

```bash
sudo pacman -Sy git
```

Após a execução desses comandos, o Git será baixado e instalado no seu sistema. Você pode verificar se a instalação foi concluída corretamente digitando o seguinte comando no terminal:

```bash
git --version
```

Isso exibirá a versão do Git instalada no seu sistema.

Se a instalação for bem-sucedida, você poderá começar a usar o Git no seu terminal.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--projetos-no-github "Subir para o topo")

---

## Clonagem dos projetos do GitHub

Abra o terminal Linux e acesse seu diretório de projetos e sega os passos seguintes:

1. No GitHub, copie a URL `HTTPS` e, digit no seu terminal o seguinte:
   ```bash
   git clone https://github.com/user/seu-diretorio.git
   ```

   > ( ! ) Todo o projeto será baixado para seu diretório local!

2. Dê todas as permissões recursivamente ao seu diretório clonado:

   ```bash
   chmod -R 777 <seu-diretorio>
   ```

   > ( ! )  Se você quiser renomeá-lo capitalizado as palavras e removendo os iféns (-) antes do commit essa é a hora!
   >
   > ```bash
   > mv <seu-diretorio> "Seu Diretório"
   > ```

3. Entre no seu diretório local de seu projeto:

   ```bash
   cd <Seu Diretóri>
   ```

4. Dê um `git status` para verificar o status do diretório:

   ```bash
   clear && git status
   ```

   > ( ! ) Irá mostrar os diretórios e arquivos em linhas vermelhas!

5. Adicione todos ao Git com o seguinte comando:

   ```bash
   git add . && clear && git status
   ```

6. Faça um commit do procedimento:

   ```bash
   git commit -m "Clone" && git log
   ```

7. E agora faça um push para finalizar:

   ```bash
   git push
   ```

Feito esse procedimento, você terá seu projeto clonado e sincronizado com o GitHub.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--projetos-no-github "Subir para o topo")

---