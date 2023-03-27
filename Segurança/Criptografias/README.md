# [React Codes](https://github.com/systemboys/React_Codes#react-codes "React Codes") / Criptografias

[![Criptografia](https://github.com/systemboys/React_Codes/raw/main/Seguran%C3%A7a/Criptografias/images/seguranca-da-informacao.jpg "Criptografia")](https://github.com/systemboys/React_Codes/raw/main/Seguran%C3%A7a/Criptografias/images/seguranca-da-informacao.jpg "Criptografia")

- [Criptografia de senhas em ReactJS usando JavaScript](#criptografia-de-senhas-em-reactjs-usando-javascript "Criptografia de senhas em ReactJS usando JavaScript")

---

## Criptografia de senhas em ReactJS usando JavaScript

No JavaScript/ReactJS, você pode utilizar a função `crypto.subtle.digest()` para gerar um hash da senha. Existem várias opções de algoritmos de hash disponíveis, como SHA-1, SHA-256 e SHA-512.

Por exemplo, para gerar um hash SHA-256 da senha, você pode utilizar o seguinte código:

```javascript
async function hashPassword(password) {
  // Converte a string da senha em ArrayBuffer
  const encoder = new TextEncoder();
  const data = encoder.encode(password);

  // Gera o hash SHA-256
  const hashBuffer = await crypto.subtle.digest('SHA-256', data);

  // Converte o ArrayBuffer em uma string hexadecimal
  const hashArray = Array.from(new Uint8Array(hashBuffer));
  const hashHex = hashArray.map(b => b.toString(16).padStart(2, '0')).join('');

  return hashHex;
}
```

Para utilizar a função `hashPassword()`, basta passar a senha como parâmetro e aguardar o resultado:

```javascript
const hashedPassword = await hashPassword('senha123');
```

Lembrando que a criptografia da senha é apenas uma das etapas importantes para garantir a segurança do sistema. É necessário tomar outras medidas, como armazenar os hashes das senhas em um formato seguro e implementar medidas para prevenir ataques de força bruta ou roubo de sessão, por exemplo.

[(&larr;) Voltar](https://github.com/systemboys/React_Codes#react-codes "Voltar ao SumÃ¡rio") | 
[(&uarr;) Subir](#criptografias "Subir para o topo")

---
