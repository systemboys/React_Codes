# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Amazon Web Services - AWS

[![Amazon Web Services](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/Group-169-3.png "Amazon Web Services")](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/Group-169-3.png "Amazon Web Services")

- [O que é computação em nuvens?](#o-que-%C3%A9-computa%C3%A7%C3%A3o-nas-nuvens "O que é computação em nuvens?")
- [Características de Cloud](#caracter%C3%ADsticas-essenciais-de-cloud "Características de Cloud")
- [Modelos de Deploy](#modelos-de-deploy "Modelos de Deploy")
- [Serviços AWS](#servi%C3%A7os-aws "Serviços AWS")
    - [IAM](#iam "IAM")
    - [EC2](#ec2 "EC2")
        - [Configurando e gerenciando instâncias EC2 na AWS](# "Configurando e gerenciando instâncias EC2 na AWS")
    - [CodePipeline](#codepipeline "CodePipeline")
    - [CodeDeply](#codedeply "CodeDeply")
    - [S3](#s3 "S3")
    - [RDS](#rds "RDS")

---

## O que é computação nas nuvens?

A computação nas nuvens, ou Cloud Computing em inglês, é um modelo de entrega de serviços de computação pela Internet, onde os recursos de processamento, armazenamento, software e outros serviços são fornecidos sob demanda para os usuários finais.

Em outras palavras, a computação nas nuvens permite que as empresas e usuários acessem recursos de computação, como servidores, armazenamento e aplicativos, de forma remota, através da Internet, em vez de ter que gerenciar seus próprios servidores e infraestrutura localmente.

Os provedores de serviços em nuvem geralmente oferecem serviços em três modelos principais:

| Modelo de Serviço | Conceito |
| :------------ | :------------ |
| Infraestrutura como Serviço (IaaS) | Nesse modelo, os provedores de serviços em nuvem fornecem recursos de infraestrutura, como servidores virtuais, armazenamento e rede, para que os usuários finais possam implantar seus próprios aplicativos e serviços. |
| Plataforma como Serviço (PaaS) | Nesse modelo, os provedores de serviços em nuvem fornecem plataformas de desenvolvimento e implantação para que os usuários finais possam criar, testar e implantar aplicativos. |
| Software como Serviço (SaaS) | Nesse modelo, os provedores de serviços em nuvem fornecem aplicativos de software prontos para uso para os usuários finais, como serviços de e-mail ou de colaboração em equipe. |

A computação nas nuvens permite que as empresas reduzam os custos de infraestrutura, aumentem a eficiência, escalabilidade e flexibilidade, e concentrem-se mais em suas atividades principais. Além disso, a computação em nuvem oferece acesso a tecnologias avançadas, como análise de dados e inteligência artificial, que muitas empresas podem não ter a capacidade de implementar localmente.

[![Modelos de Serviços](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/Modelo-de-Servi%C3%A7os.png "Modelos de Serviços")](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/Modelo-de-Servi%C3%A7os.png "Modelos de Serviços")

Responsabilidade dos modelos.

[![Profissionais de TI](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/Profissionais-de-TI.png "Profissionais de TI")](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/Profissionais-de-TI.png "Profissionais de TI")

| Modelo | Responsabilidade |
| :------------ | :------------ |
| Traditional IT | O TI tradicional tem a responsabilidade de tudo. O TI tem que cuidar da rede, cabeamento, os storeges, servidores físicos, rack, virtualização, o sistema operacional que está rodando, softwares no sistema operacional, versões de aplicações, bancos de dados, os dados em si no banco de dados e as aplicações. |
| IaaS | Nesse modelo, o TI não precisa mais se preocupar com rede e cabeamento, storage, servidores, virtualizador, sendo uma responsabilidade do provedor de Cloud, no nosso caso aqui, a AWS. Mas nesse modelo, o TI ainda tem algumas responsabilidades como o sistema operacional, o que será instalado nesse sistema operacional, os dados e colocar as aplicações para rodar. |
| PaaS | Nesse modelo, o TI só deve se preocupar com os dados e com as aplicações. Para o TI não interessa se estará rodando em Windows ou Linux, se está com os Paths de segurança, ele apenas colocará suas aplicações e dados. Sendo a grande tendência de de mercado é a utilização de PaaS. Por ser mais prático, mais barato, entregar mais qualidade e serviços. |
| SaaS | Nesse modelo, é o que o usuário utiliza no dia a dia como e-mails, Netflix, gerenciamento de diretórios como OneDrive, GoogleDrive, DropBox etc. |

> As empresas utilizam de IaaS e PaaS, infraestruturas como serviços para entregar um SaaS, um software como serviço.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

---

## Características essenciais de Cloud?

Existem várias características essenciais que definem a computação em nuvem (Cloud Computing). Aqui estão algumas das principais:

| Característica | Conceito |
| :------------ | :------------ |
| Elasticidade | A computação em nuvem permite que os recursos de computação, armazenamento e rede sejam facilmente escalados para cima ou para baixo, conforme necessário. Isso significa que você pode lidar com picos de tráfego ou demanda sem ter que investir em hardware adicional. |
| Automação | A nuvem é altamente automatizada, o que significa que muitas das tarefas manuais associadas à gestão de infraestrutura tradicional são tratadas automaticamente. Isso ajuda a reduzir erros humanos e a aumentar a eficiência. |
| Pagamento conforme o uso | Em vez de pagar antecipadamente por capacidade de computação, a nuvem permite que você pague apenas pelo que usa. Isso pode ser especialmente benéfico para empresas que têm necessidades flutuantes de computação ao longo do tempo. |
| Acesso global | A nuvem permite que você acesse seus recursos de qualquer lugar do mundo, desde que tenha uma conexão com a Internet. Isso pode ser especialmente útil para empresas com escritórios em vários locais ou para colaboração remota. |

| Segurança | A nuvem é altamente segura, com várias camadas de proteção de dados e infraestrutura para garantir a privacidade e segurança dos dados dos usuários. |

Essas são apenas algumas das características essenciais da computação em nuvem, mas elas ajudam a explicar por que a nuvem se tornou tão popular para empresas de todos os tamanhos e setores.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

## Modelos de Deploy

Os modelos de deploy (implantação) são formas diferentes de disponibilizar e instalar um aplicativo ou software em um ambiente de produção. Existem vários modelos de deploy, cada um com suas próprias vantagens e desvantagens. Aqui estão alguns dos modelos mais comuns:

| Modelo | Conceito |
| :------------ | :------------ |
| On-Premises | Este modelo envolve a instalação de software em hardware local, geralmente em servidores que estão fisicamente localizados na empresa ou em um data center da empresa. Este modelo oferece controle total sobre o ambiente, mas pode ser mais caro em termos de investimento inicial em hardware e software, além de exigir mais recursos de manutenção e gerenciamento. |
| Cloud (nuvem) | Neste modelo, o software é implantado em servidores remotos que são gerenciados por provedores de serviços em nuvem. Os provedores de serviços em nuvem fornecem recursos de computação, armazenamento e rede sob demanda, geralmente com base em um modelo de pagamento conforme o uso. Este modelo oferece escalabilidade, eficiência e flexibilidade, mas pode ter preocupações com a segurança e privacidade de dados. |
| Híbrido | Este modelo combina elementos dos modelos On-Premises e Cloud, permitindo que as empresas aproveitem os benefícios de ambos. Por exemplo, um aplicativo pode ser implantado em um ambiente On-Premises, mas pode usar recursos em nuvem para lidar com picos de tráfego ou demanda. |
| Container | Neste modelo, o aplicativo é implantado em um container, que é uma unidade de software que inclui todos os componentes necessários para executar o aplicativo. Os containers são altamente portáteis e podem ser executados em qualquer ambiente de hospedagem que suporte containers, como Kubernetes ou Docker. |
| Serverless | Este modelo envolve a implantação de código em um ambiente gerenciado, em que o provedor de serviços gerencia automaticamente o dimensionamento, o provisionamento e o gerenciamento de recursos. O desenvolvedor fornece apenas o código do aplicativo, e o provedor de serviços em nuvem gerencia todo o resto. Este modelo oferece escalabilidade e eficiência, mas pode ter limitações em termos de controle sobre o ambiente de hospedagem. |

Cada modelo de deploy tem suas próprias vantagens e desvantagens, e a escolha do modelo adequado dependerá das necessidades específicas da empresa e do aplicativo em questão.

[![Modelos de Deploy](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/Modelos-de-Deploy.png "Modelos de Deploy")](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/Modelos-de-Deploy.png "Modelos de Deploy")

Na imagem acima, há alguns modelos de Deploy que existem, lembrando que há vários tipos de nuvens.

| Tipo | Descrição |
| :------------ | :------------ |
| Nuvem privada | É quando você tem um Datacenter, onde nesse datacenter roda alguma plataforma de Claud e, só a sua empresa utiliza este datacenter. |
| Nuvem pública | É quando você tem um Datacenter onde várias empresas consomem os recursos desses datacenters. O fato de você criar uma nuvem pública, não significa que seus dados são públicos. Você pode criar uma nuvem pública e ter um ambiente privado dentro dele. Exemplo: Você pode usar a AWS e ser acessível apenas de dentro da sua empresa. |
| Nuvem híbrida | Onde você utiliza algo em ambiente local, mas também utiliza de uma nuvem pública. |
| Nuvem comunitária | É uma nuvem privada, só que para uma comunidade. Exemplo: O governo do seu estado criou uma nuvem comunitária onde quem vai utilizar é o governo, a polícia militar, bombeiros, secretarias etc. |

> Hoje, mais de 90% das empresas são nuvens públicas e o restante acabam usando nuvem privadas, sendo usando nuvems públicas em todos os pontos. Inclusive grandes bancos estão migrando para nuvems públicas por causa das questões de segurança.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

---

## Serviços AWS

[![Serviços AWS](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/AWS_services.png "Serviços AWS")](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/AWS_services.png "Serviços AWS")

| Serviço | Descrição |
| :------------: | :------------ |
| IAM | Serviço de gerenciamento de identidade e acesso que controla o acesso aos recursos da AWS. |
| EC2 | Serviço de computação em nuvem que permite criar e gerenciar instâncias de servidores virtuais. |
| CodePipeline | Serviço de integração e entrega contínua (CI/CD) que automatiza o processo de release de software. |
| CodeDeply | Serviço que permite automatizar o deploy de aplicações em diferentes ambientes. |
| S3 | Serviço de armazenamento em nuvem que permite armazenar e recuperar dados de forma segura e escalável. |
| RDS | Serviço de banco de dados relacional gerenciado que permite implantar, operar e escalar bancos de dados na nuvem. |

[![Serviços AWS](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/AWS_services_icons.png "Serviços AWS")](https://github.com/systemboys/React_Codes/raw/main/Computa%C3%A7%C3%A3o%20em%20nuvens/AWS/images/AWS_services_icons.png "Serviços AWS")

## IAM

O IAM (Identity and Access Management) é um serviço da AWS que oferece controle de acesso seguro aos recursos da conta da AWS. Ele permite gerenciar o acesso de usuários e aplicativos a recursos da AWS de forma granular, definindo permissões específicas para cada recurso.

Com o IAM, é possível criar usuários e grupos, definir permissões detalhadas para acesso aos serviços e recursos da AWS, criar políticas de acesso personalizadas, gerenciar chaves de acesso e credenciais de segurança, além de monitorar e auditar as atividades de usuários e aplicativos.

O IAM é uma ferramenta essencial para garantir a segurança dos recursos da AWS, permitindo a criação de ambientes seguros e controlados, com o mínimo de privilégios necessários para cada usuário ou aplicativo. Com o IAM, é possível controlar de forma efetiva quem tem acesso a quais recursos, além de gerenciar e auditar as atividades desses usuários e aplicativos.

[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

## EC2

EC2 (Elastic Compute Cloud) é um serviço de computação em nuvem da AWS que permite criar e executar instâncias de servidores virtuais na nuvem. Com o EC2, é possível criar, dimensionar e gerenciar instâncias de servidores com facilidade e flexibilidade, de acordo com as necessidades específicas de cada aplicação. 

O EC2 oferece diversos tipos de instâncias, com diferentes configurações de CPU, memória, armazenamento e rede, para atender a diferentes cargas de trabalho, desde aplicações simples até ambientes de alta performance. Além disso, é possível escolher entre instâncias sob demanda, reservadas ou spot, dependendo das necessidades de capacidade e do orçamento disponível.

O serviço também permite criar imagens de máquinas virtuais personalizadas, chamadas AMIs (Amazon Machine Images), que podem ser usadas para lançar novas instâncias ou replicar ambientes de produção com facilidade.

O EC2 é altamente escalável e pode ser integrado com outros serviços da AWS, como o Elastic Load Balancing (ELB) e o Auto Scaling, para garantir alta disponibilidade e escalabilidade automática da infraestrutura. Ele também pode ser usado em conjunto com outros serviços da AWS, como o Amazon RDS (Relational Database Service) e o Amazon S3 (Simple Storage Service), para criar soluções completas e escaláveis na nuvem.

[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

## CodePipeline

O AWS CodePipeline é um serviço de integração e entrega contínua (CI/CD) totalmente gerenciado pela AWS que ajuda a automatizar o processo de lançamento de software, desde a compilação do código-fonte até a implantação em produção. Ele permite a criação de pipelines de entrega contínua que automatizam a compilação, teste e implantação de aplicativos. 

O CodePipeline pode ser integrado a várias ferramentas de terceiros, como o Jenkins e o GitHub, bem como com serviços da AWS, como o AWS CodeBuild, o AWS CodeDeploy e o AWS Elastic Beanstalk, permitindo que os desenvolvedores personalizem os pipelines para atender às suas necessidades específicas. 

O serviço também inclui recursos avançados de monitoramento e rastreamento de fluxos de trabalho, permitindo que os desenvolvedores monitorem todo o processo de lançamento, identifiquem rapidamente possíveis problemas e implementem correções de bugs em tempo real. Além disso, o CodePipeline é altamente escalável e pode ser usado para implantar aplicativos em uma ampla gama de ambientes, incluindo instâncias do Amazon EC2, contêineres do Docker e serviços sem servidor do AWS Lambda.

[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

## CodeDeply

CodeDeploy é um serviço de implantação automatizada da AWS que permite aos usuários automatizar a implantação de aplicativos em diferentes ambientes, como instâncias do Amazon EC2, servidores localizados no local, etc. O CodeDeploy facilita a implantação rápida e consistente de aplicativos em diferentes ambientes, com redução de tempo e riscos. Ele permite que os usuários implementem implantações sem tempo de inatividade e monitorem o status das implantações em tempo real. O CodeDeploy é flexível e pode ser integrado com outras ferramentas de desenvolvimento, como o AWS CodeCommit, AWS CodePipeline e outras ferramentas de terceiros. Com o CodeDeploy, é possível automatizar as atualizações de aplicativos em um ambiente, tornando o processo mais ágil, escalável e seguro.

[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

## S3

O Amazon S3 (Simple Storage Service) é um serviço de armazenamento de objetos altamente escalável e durável da AWS (Amazon Web Services). Ele permite que os usuários armazenem e recuperem quantidades praticamente ilimitadas de dados de forma segura e confiável por meio de uma interface web simples. 

Os objetos armazenados no S3 podem variar de alguns bytes até terabytes de tamanho, e podem ser acessados ​​de qualquer lugar com acesso à Internet. Além disso, o Amazon S3 permite que os usuários armazenem e recupere dados em vários formatos, incluindo imagens, vídeos, arquivos de áudio, documentos e muito mais.

O S3 da AWS possui alta disponibilidade, durabilidade e segurança, garantindo a integridade dos dados armazenados. Ele também oferece recursos de gerenciamento de ciclo de vida, controle de acesso e recursos de análise para ajudar os usuários a gerenciar seus dados de maneira eficaz e eficiente.

[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

## RDS

O Amazon Relational Database Service (RDS) é um serviço de banco de dados gerenciado oferecido pela Amazon Web Services (AWS) que permite aos usuários configurar, operar e escalar bancos de dados relacionais na nuvem. O RDS oferece suporte a vários bancos de dados relacionais, incluindo MySQL, PostgreSQL, Oracle, SQL Server e Amazon Aurora.

O RDS gerencia tarefas de administração de banco de dados, como backup, replicação, atualizações de software e aplicação de patches de segurança. Ele também oferece recursos para monitorar a integridade do banco de dados, ajustar o desempenho e escalar verticalmente ou horizontalmente a capacidade do banco de dados.

O RDS é altamente escalável, o que significa que os usuários podem aumentar ou diminuir a capacidade do banco de dados com facilidade, de acordo com as necessidades do aplicativo ou da empresa. Além disso, o RDS fornece opções de segurança avançadas, incluindo a criptografia de dados em trânsito e em repouso, bem como a integração com o AWS Identity and Access Management (IAM) para controle de acesso baseado em funções.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao Sumário") | 
[(&uarr;) Subir](#react-codes--amazon-web-services---aws "Subir para o topo")

---