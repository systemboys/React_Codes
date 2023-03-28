# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Emails

[![Imagem 1](https://site.com/img/exemplo.png "Imagem 1")](http://link.com "Imagem 1")

- [Link 1](https://site.com#anchor-link-1 "Link 1")

---

## Envio de e-mails com ReactJS utilizando o serviço de e-mail escolhido

Para enviar e-mails com ReactJS, você precisará de um backend para processar o envio. O ReactJS é uma biblioteca de frontend e não é capaz de enviar e-mails diretamente.

Uma opção é criar um endpoint na sua API para receber as informações do formulário e enviar o e-mail a partir do backend. Você pode usar uma biblioteca de envio de e-mail em Node.js, como o Nodemailer.

O fluxo seria o seguinte: o usuário preenche o formulário no frontend, o ReactJS envia uma requisição para a sua API contendo as informações do formulário e o backend processa essa requisição, enviando o e-mail.

Abaixo segue um exemplo de como você poderia criar um endpoint em Node.js utilizando o Nodemailer:

```javascript
const express = require('express');
const nodemailer = require('nodemailer');
const bodyParser = require('body-parser');

const app = express();

// Configurando o body-parser para lidar com as requisições POST
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());

// Endpoint para receber as informações do formulário e enviar o e-mail
app.post('/enviar-email', (req, res) => {
  const { nome, email, mensagem } = req.body;

  // Configurando o Nodemailer com as informações do seu servidor de e-mail
  const transporter = nodemailer.createTransport({
    host: 'smtp.seuservidordeemail.com',
    port: 587,
    secure: false,
    auth: {
      user: 'seuemail@seuservidordeemail.com',
      pass: 'suasenha',
    },
  });

  // Configurando o e-mail que será enviado
  const mailOptions = {
    from: 'seuemail@seuservidordeemail.com',
    to: 'emaildedestino@dominio.com',
    subject: 'Contato pelo formulário de contato',
    text: `Nome: ${nome}\nE-mail: ${email}\nMensagem: ${mensagem}`,
  };

  // Enviando o e-mail
  transporter.sendMail(mailOptions, (error, info) => {
    if (error) {
      console.log(error);
      res.status(500).send('Erro ao enviar e-mail');
    } else {
      console.log(`E-mail enviado: ${info.response}`);
      res.send('E-mail enviado com sucesso');
    }
  });
});

app.listen(3000, () => {
  console.log('Servidor rodando na porta 3000');
});
```

No exemplo acima, o endpoint `/enviar-email` recebe as informações do formulário (nome, email e mensagem) e configura o Nodemailer com as informações do servidor de e-mail e do e-mail que será enviado. Em seguida, o e-mail é enviado utilizando o método `transporter.sendMail()`. Se ocorrer algum erro, a API retorna um status 500 e, caso contrário, retorna um status 200 indicando que o e-mail foi enviado com sucesso.

No ReactJS, você pode enviar a requisição para o endpoint utilizando o `fetch()` ou uma biblioteca de requisições HTTP, como o Axios. O código abaixo é um exemplo utilizando o Axios:

```javascript
import axios from 'axios';

function enviarEmail(nome, email, mensagem) {
  const data = { nome, email, mensagem };

  axios.post('/enviar-email', data)
    .then(response => {
      console.log(response.data);
    })
    .catch(error => {
      console.log(error);
    });
}
```

No exemplo acima, estamos usando a biblioteca Nodemailer para enviar um email de um endereço de email SMTP configurado para a nossa conta de email. Você precisará fornecer as credenciais de login e senha do seu email SMTP.

Para usar esta função em seu código React, você pode simplesmente importá-la em seu componente e chamá-la quando necessário. Por exemplo, em um formulário de contato, você poderia chamar a função handleSubmit() quando o formulário for submetido, passando os dados do formulário para a função como um parâmetro.

Lembre-se de que, para usar esta função, você precisará ter uma conta de email SMTP configurada e ter as credenciais de login e senha disponíveis. Além disso, certifique-se de que o seu servidor esteja configurado para permitir o envio de emails através do protocolo SMTP.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#assunto "Subir para o topo")

---