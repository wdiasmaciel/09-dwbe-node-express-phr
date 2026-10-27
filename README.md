# 09-dwbe-node-express-phr

Link:

https://app.notion.com/p/Express-js-7e344ced362582388270818c6c75f57b

---

## Comandos Iniciais

```bash
sudo apt update
```

```bash
sudo apt install -y nodejs
```

```bash
node -v
```

```bash
npm install -g npm@11.19.0
```

```bash
npm -v
```

```bash
mkdir api-express
```

```bash
cd api-express
```

```bash
npm init -y
```

No arquivo `package.json`, substituir ` "type": "commonjs"` por ` "type": "module"`:

```text
{
  "name": "api-express",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "type": "module"
}
```

Instalar o `Express`:

```bash
npm install express
```

```js
{
  "name": "api-express",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "type": "module",
  "dependencies": {
    "express": "^5.3.0"
  }
}
```

---

## Servidor 01

Criar o arquivo:

```jsx
01-server.js
```

```js
import express from 'express';

const app = express();

app.get("/", (req, res) => {
  res.send("API funcionando!");
});

app.listen(3000, () => {
  console.log("Servidor rodando na porta 3000");
});
```

Executar o servidor:

```bash
node 01-server.js
```

Abrir no navegador:

```text
http://localhost:3000
```

Resposta:

```text
API funcionando!
```
---

## Servidor 02

Criar o arquivo:

```jsx
02-server.js
```

```js
const express = require("express");

const app = express();

app.use(express.json());

app.get("/", (req, res) => {
  res.json({
    mensagem: "API funcionando",
  });
});

app.listen(3000, () => {
  console.log("Servidor rodando na porta 3000");
});
```