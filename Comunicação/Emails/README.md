# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Emails

[![Envio de Emails](https://github.com/systemboys/React_Codes/raw/main/Comunica%C3%A7%C3%A3o/Emails/images/SendMail1.png "Envio de Emails")](https://github.com/systemboys/React_Codes/raw/main/Comunica%C3%A7%C3%A3o/Emails/images/SendMail1.png "Envio de Emails")

- [Enviar e-mails com Node.js utilizando o pacote Nodemailer](#enviar-e-mails-com-nodejs-utilizando-o-pacote-nodemailer "Enviar e-mails com Node.js utilizando o pacote Nodemailer")

---

## Enviar e-mails com Node.js utilizando o pacote Nodemailer

Para enviar e-mails com Node.js utilizando o pacote Nodemailer, você precisa configurar um servidor de e-mail válido, como um serviço SMTP. Depois de configurar um servidor de e-mail válido, você pode instalar o pacote Nodemailer no seu projeto ReactJS usando o npm:

```bash
npm install nodemailer
```

Em seguida, você pode criar uma função para enviar o e-mail no componente "ContactTheDeveloper". Para isso, adicione o código abaixo:

```jsx
import nodemailer from 'nodemailer';

async function sendEmail() {
  // Crie um objeto com as informações do seu servidor SMTP.
  let transporter = nodemailer.createTransport({
    host: 'seu.servidor.de.email',
    port: 587,
    secure: false,
    auth: {
      user: 'seu_usuario',
      pass: 'sua_senha'
    }
  });

  // Crie um objeto com as informações do e-mail que será enviado.
  let mailOptions = {
    from: 'seu_usuario',
    to: 'destinatario',
    subject: 'Assunto do e-mail',
    text: 'Mensagem do e-mail'
  };

  // Envie o e-mail.
  await transporter.sendMail(mailOptions);
}
```

Substitua as informações do servidor SMTP pelas informações do seu próprio servidor de e-mail e substitua as informações do e-mail pelo seu próprio conteúdo. Depois, chame a função "sendEmail" dentro da função "handleSubmitContact":

```jsx
// Importe o pacote nodemailer.
import nodemailer from 'nodemailer';

// Função para enviar e-mails.
async function sendEmail() {
  // Crie um objeto com as informações do seu servidor SMTP.
  let transporter = nodemailer.createTransport({
    host: 'seu.servidor.de.email',
    port: 587,
    secure: false,
    auth: {
      user: 'seu_usuario',
      pass: 'sua_senha'
    }
  });

  // Crie um objeto com as informações do e-mail que será enviado.
  let mailOptions = {
    from: 'seu_usuario',
    to: 'destinatario',
    subject: 'Assunto do e-mail',
    text: 'Mensagem do e-mail'
  };

  // Envie o e-mail.
  await transporter.sendMail(mailOptions);
}

export function ContactTheDeveloper() {
  // ... Código anterior

  // Função para enviar o formulário.
  async function handleSubmitContact(e) {
    e.preventDefault();

    // Verifique se os campos do formulário estão preenchidos corretamente.
    // ...

    // Envia o e-mail.
    await sendEmail();

    // Exibir no console os valores obtidos nos campos.
    console.log("Submit", { name, email, subject, message });

    // Resetar após enviar os dados.
    handleReset();
  }

  // ... Código posterior
}
```

Lembre-se de substituir as informações do servidor SMTP pelas informações do seu próprio servidor de e-mail e substituir as informações do e-mail pelo seu próprio conteúdo. Com isso, ao submeter o formulário, o e-mail será enviado para o endereço de destino especificado no objeto "mailOptions".

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#react-codes--emails "Subir para o topo")

---