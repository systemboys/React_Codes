# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Node.JS

[![Node.JS](https://github.com/systemboys/React_Codes/raw/main/Ambientes%20de%20execu%C3%A7%C3%A3o/NodeJS/images/Node.js.jpg "Node.JS")](https://github.com/systemboys/React_Codes/raw/main/Ambientes%20de%20execu%C3%A7%C3%A3o/NodeJS/images/Node.js.jpg "Node.JS")

- [O que é Node.js?](#o-que-%C3%A9-nodejs "O que é Node.js?")
- [Como funciona?](#como-funciona "Como funciona?")
- [Principais vantagens](#principais-vantagens "Principais vantagens")
- [Node Version Manager (nvm)](#node-version-manager-nvm "Node Version Manager (nvm)")
    - [Como instalar?](#como-instalar "Como instalar?")
    - [Comandos básicos do NVM para gerenciamento de versões do Node.js](#comandos-b%C3%A1sicos-do-nvm-para-gerenciamento-de-vers%C3%B5es-do-nodejs "Comandos básicos do NVM para gerenciamento de versões do Node.js")
- [Resolvendo o erro de porta em uso no servidor Node.js](#resolvendo-o-erro-de-porta-em-uso-no-servidor-nodejs "Resolvendo o erro de porta em uso no servidor Node.js")
- [Inicializar novo projeto Node.js criando arquivo 'package.json' com valores padrão.](#inicializar-novo-projeto-nodejs-criando-arquivo-packagejson-com-valores-padr%C3%A3o "Inicializar novo projeto Node.js criando arquivo 'package.json' com valores padrão.")

---

## O que é Node.js?

Node.js é um ambiente de execução JavaScript que permite executar aplicações desenvolvidas com a linguagem de forma autônoma, sem depender de um navegador. Com ele, é possível criar praticamente qualquer tipo de aplicações web, desde servidores para sites estáticos e dinâmicos, até APIs e sistemas baseados em microserviços.

Foi criado em 2009 pelo engenheiro de software Ryan Dahl como uma alternativa ao Apache HTTP Server, o servidor web mais popular da época. Dahl criticava algumas limitações do Apache, como o suporte relativamente baixo a múltiplas conexões, buscando resolver este problema com uma abordagem focada em eventos e execução assíncrona, sendo uma opção mais responsiva e com menos consumo de recursos do que os servidores “tradicionais”.

Atualmente, o Node.js é mantido pela [OpenJS Foundation](https://openjsf.org/ "OpenJS Foundation’s mission is to drive broad adoption and ongoing development of key JavaScript solutions and related technologies."), uma fundação criada em 2019 com o objetivo de promover a utilização do JavaScript e de suas tecnologias relacionadas.

[⏹️](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio")
[🔼](#react-codes--nodejs "Subir para o topo")

---

## Como funciona?

A principal característica do Node.js é sua execução ser single-thread, ou seja, os recursos computacionais são alocados apenas uma vez pelo tempo que a aplicação estiver sendo executada. Aplicações multi-thread, como as criadas com PHP, por exemplo, requerem a criação de uma thread a cada nova requisição, e ela não é executada enquanto a anterior não for finalizada.

Essa thread única é chamada de “Event Loop”. Ela trata todas as requisições como eventos, de maneira assíncrona e não-bloqueável, eliminando a necessidade de filas de processamento e tornando as aplicações mais eficientes e responsivas.

O Node.js não é um framework JavaScript, como o React ou o Vue.js, mas sim um ambiente de execução em uma máquina virtual própria para interpretar e executar os scripts de forma autônoma, baseada no “motor” V8, criado pelo Google para o navegador Chrome.

[![Código JavaScript](https://github.com/systemboys/React_Codes/blob/main/Ambientes%20de%20execu%C3%A7%C3%A3o/NodeJS/images/o_que_e_node_js-e1612977170388-700x393.jpg?raw=true "Código JavaScript")](https://github.com/systemboys/React_Codes/blob/main/Ambientes%20de%20execu%C3%A7%C3%A3o/NodeJS/images/o_que_e_node_js-e1612977170388-700x393.jpg?raw=true "Código JavaScript")

> Código Javascript (Imagem: Ferenc Almasi / Unsplash)

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Principais vantagens

Devido ao baixo consumo de recursos e à capacidade de processar várias requisições simultaneamente, o Node.js é muito utilizado em aplicações que requerem uma alta escalabilidade, ou seja, que possam crescer sem perder qualidade ou aumentar os custos.

Outra vantagem é a possibilidade de manter o ecossistema de aplicações e toda a base de código em uma só linguagem de programação, no caso, o JavaScript. Também há o [NPM](https://www.npmjs.com/ "Node Package Manager") (Node Package Manager), o gerenciador de pacotes do Node.js, que dá acesso a um enorme repositório de bibliotecas e módulos que podem ser adicionadas ao projeto, contendo ferramentas e/ou soluções para os mais diversos problemas e requisitos.

O Node.js é um software gratuito, de código-aberto e com uma comunidade ativa e participativa. É suportado pelos mais diversos serviços de hospedagem, com AWS, Google Could e Microsoft Azure, e amplamente utilizado em escala industrial por grandes empresas como Netflix, PayPal, Linkedin, entre outras. Você pode saber mais sobre o Node.js acessando o [site oficial](https://nodejs.org/en/ "Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine.").

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Node Version Manager (nvm)

NVM (Node Version Manager) é uma ferramenta utilizada para gerenciar as versões do Node.js instaladas em um sistema. Com o NVM, é possível instalar, desinstalar e alternar entre diferentes versões do Node.js em um mesmo ambiente, permitindo que desenvolvedores e equipes trabalhem com diferentes projetos que requerem diferentes versões do Node.js.

O NVM funciona instalando as diferentes versões do Node.js em diretórios distintos e permitindo que o usuário as acesse por meio de comandos no terminal. Isso facilita o gerenciamento das versões, garantindo que cada projeto tenha a versão correta do Node.js sem interferir em outras aplicações.

Além disso, o NVM permite que as diferentes versões do Node.js coexistam em um mesmo ambiente, permitindo que o desenvolvedor possa testar e executar seus projetos em diferentes versões do Node.js sem precisar desinstalar e reinstalar a versão desejada manualmente.

O NVM é compatível com Linux, macOS e Windows e pode ser instalado por meio de um script de instalação ou por meio do gerenciador de pacotes do sistema operacional.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Como instalar?

Para instalar o Node.js, siga os seguintes passos:

1. Acesse o site oficial do Node.js em [https://nodejs.org/](https://nodejs.org/ "Site oficial do Node.js").

2. Clique no botão "Baixar" (Download).

3. Selecione a versão recomendada para a maioria dos usuários ou escolha uma versão específica.

4. Escolha o sistema operacional que você está usando (Windows, macOS, Linux, etc).

5. Baixe o instalador correspondente.

6. Execute o instalador e siga as instruções para concluir a instalação.

Ao concluir a instalação, você poderá verificar se o Node.js foi instalado corretamente abrindo o terminal ou prompt de comando e digitando o comando `node -v`. Se o Node.js estiver instalado corretamente, o terminal deve exibir a versão instalada.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Comandos básicos do NVM para gerenciamento de versões do Node.js

Alguns comandos para lidar com versões:

Listar as versões do Node.js.

```bash
nvm list
```

> O comando `nvm list` é usado para listar todas as versões do Node.js que foram instaladas no seu computador através do NVM (Node Version Manager). Ele mostra todas as versões do Node.js que você tem disponível, com a versão atual realçada em verde. Também indica qual é a versão padrão do Node.js que será usada se você não especificar uma versão específica do Node.js. Isso é útil para ver as versões do Node.js que estão disponíveis para uso e selecionar a versão apropriada para o seu projeto.

Verificar a versão mais recente do Node.js.

```bash
npm view node version
```

> Isso deve retornar a versão mais recente do Node.js disponível no registro do npm. Se você preferir, também pode verificar a versão mais recente diretamente no site oficial do Node.js.

Instalar uma versão específica do Node.js

```bash
nvm install <version>
```

Selecionar entre várias instaladas a versão do Node.js que será usada no momento.

```bash
nvm use <version>
```

Este comando define a versão do node.js que você deseja usar. Se você quiser que esta versão seja usada por padrão, você pode usar o comando:

```jsx
nvm alias default <version>
```

Esses comandos estão relacionados ao gerenciador de versões do Node.js chamado Node Version Manager (nvm).

- O comando `nvm list` é usado para listar as versões do Node.js instaladas no sistema e identificar qual versão está atualmente em uso.

- O comando `nvm install <version>` é usado para instalar uma versão específica do Node.js. Por exemplo, `nvm install 14.17.5` irá instalar a versão 14.17.5 do Node.js.

- O comando `nvm use <version>` é usado para selecionar a versão do Node.js que será usada no momento. Por exemplo, `nvm use 14.17.5` irá selecionar a versão 14.17.5 do Node.js para uso. Ao usar esse comando, o nvm ajusta as variáveis de ambiente para apontar para a versão selecionada.

- Com o comando `nvm alias default <version>`, a versão será definida como padrão, e você poderá utilizá-la sempre que abrir um novo terminal. Para confirmar que a versão padrão foi alterada, você pode usar o comando: `nvm list`.

- Feito essas alterações, faça o seguinte comando:

    ```bash
    npm i --force
    ```

    > Esse `--force` para o caso de apresentar erros.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Resolvendo o erro de porta em uso no servidor Node.js

Esse erro ocorre porque a porta 3333 já está em uso. Você pode verificar quais processos estão usando essa porta digitando o seguinte comando no terminal:

```bash
sudo lsof -i :3333
```

Isso deve retornar informações sobre o processo que está usando a porta. Em seguida, você pode finalizar o processo usando o seguinte comando:

```bash
sudo kill <PID>
```

Substitua `<PID>` pelo ID do processo que está usando a porta 3333. Depois de finalizar o processo, você deve conseguir executar novamente o comando `npm run dev` sem problemas.

> O NPM é um servidor?

NPM é a sigla para Node Package Manager, que é um gerenciador de pacotes para a plataforma Node.js. Ele é usado para instalar, gerenciar e compartilhar pacotes de código JavaScript que podem ser executados no ambiente Node.js. 

O NPM pode ser utilizado para criar servidores web, mas ele não é em si um servidor. Quando você executa o comando `npm run dev`, você está na verdade rodando um script definido no arquivo `package.json` que pode iniciar um servidor local. 

O servidor é criado através do código definido em um arquivo específico, geralmente chamado de `server.js` ou `index.js`. Esse arquivo utiliza algum framework de servidor web como o Express ou o Koa, e define rotas e respostas para as requisições que chegam ao servidor. 

Portanto, o servidor NPM em si não existe, mas o NPM pode ser utilizado para instalar e gerenciar pacotes que são utilizados em servidores web construídos em Node.js.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Inicializar novo projeto Node.js criando arquivo 'package.json' com valores padrão

```bash
npm init -y
```

O comando "npm init -y" é usado para inicializar um novo projeto Node.js e criar um arquivo "package.json" com valores padrão. O parâmetro "-y" significa "yes" (sim) e indica que todas as perguntas durante a inicialização do projeto devem ser respondidas automaticamente com os valores padrão. Isso economiza tempo, pois não é necessário responder manualmente a cada pergunta durante o processo de inicialização do projeto. O arquivo "package.json" contém informações sobre o projeto, como nome, versão, dependências e scripts.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---