# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Node.JS

[![Node.JS](https://github.com/systemboys/React_Codes/raw/main/Ambientes%20de%20execu%C3%A7%C3%A3o/NodeJS/images/Node.js.jpg "Node.JS")](https://github.com/systemboys/React_Codes/raw/main/Ambientes%20de%20execu%C3%A7%C3%A3o/NodeJS/images/Node.js.jpg "Node.JS")

- [O que é Node.js?](#o-que-%C3%A9-nodejs "O que é Node.js?")
- [Como funciona?](#como-funciona "Como funciona?")
- [Principais vantagens](#principais-vantagens "Principais vantagens")
- [Node Version Manager (nvm)](# "Node Version Manager (nvm)")
    - [Como instalar?](#como-instalar "Como instalar?")
    - [Comandos básicos do NVM para gerenciamento de versões do Node.js](# "Comandos básicos do NVM para gerenciamento de versões do Node.js")

---

## O que é Node.js?

Node.js é um ambiente de execução JavaScript que permite executar aplicações desenvolvidas com a linguagem de forma autônoma, sem depender de um navegador. Com ele, é possível criar praticamente qualquer tipo de aplicações web, desde servidores para sites estáticos e dinâmicos, até APIs e sistemas baseados em microserviços.

Foi criado em 2009 pelo engenheiro de software Ryan Dahl como uma alternativa ao Apache HTTP Server, o servidor web mais popular da época. Dahl criticava algumas limitações do Apache, como o suporte relativamente baixo a múltiplas conexões, buscando resolver este problema com uma abordagem focada em eventos e execução assíncrona, sendo uma opção mais responsiva e com menos consumo de recursos do que os servidores “tradicionais”.

Atualmente, o Node.js é mantido pela OpenJS Foundation, uma fundação criada em 2019 com o objetivo de promover a utilização do JavaScript e de suas tecnologias relacionadas.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

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

Outra vantagem é a possibilidade de manter o ecossistema de aplicações e toda a base de código em uma só linguagem de programação, no caso, o JavaScript. Também há o NPM (Node Package Manager), o gerenciador de pacotes do Node.js, que dá acesso a um enorme repositório de bibliotecas e módulos que podem ser adicionadas ao projeto, contendo ferramentas e/ou soluções para os mais diversos problemas e requisitos.

O Node.js é um software gratuito, de código-aberto e com uma comunidade ativa e participativa. É suportado pelos mais diversos serviços de hospedagem, com AWS, Google Could e Microsoft Azure, e amplamente utilizado em escala industrial por grandes empresas como Netflix, PayPal, Linkedin, entre outras. Você pode saber mais sobre o Node.js acessando o site oficial.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Node Version Manager (nvm)

...

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Como instalar?

...

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---

## Comandos básicos do NVM para gerenciamento de versões do Node.js

Alguns comandos para lidar com versões:

Listar as versões do Node.js.

```bash
nvm list
```

Instalar uma versão específica do Node.js

```bash
nvm install <version>
```

Selecionar a versão do Node.js que será usada no momento.

```bash
nvm use <version>
```

Esses comandos estão relacionados ao gerenciador de versões do Node.js chamado Node Version Manager (nvm).

- O comando `nvm list` é usado para listar as versões do Node.js instaladas no sistema e identificar qual versão está atualmente em uso.

- O comando `nvm install <version>` é usado para instalar uma versão específica do Node.js. Por exemplo, `nvm install 14.17.5` irá instalar a versão 14.17.5 do Node.js.

- O comando `nvm use <version>` é usado para selecionar a versão do Node.js que será usada no momento. Por exemplo, `nvm use 14.17.5` irá selecionar a versão 14.17.5 do Node.js para uso. Ao usar esse comando, o nvm ajusta as variáveis de ambiente para apontar para a versão selecionada.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--nodejs "Subir para o topo")

---