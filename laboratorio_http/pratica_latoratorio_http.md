# Laboratório – Protocolo HTTP com Servidor Apache

## Objetivo
Nesta prática os alunos irão:
- Entender os conceitos básicos do protocolo **HTTP**.  
- Aprender a **hospedar uma página web** simples usando o **servidor Apache**.  
- Acessar a página via navegador utilizando **HTTP**.  

---

## Conceitos de HTTP

- **HTTP (HyperText Transfer Protocol)** é o protocolo usado para comunicação entre **clientes (navegadores)** e **servidores web**.  
- O cliente envia uma **requisição HTTP** (request) ao servidor.  
- O servidor responde com uma **resposta HTTP** (response), que geralmente contém páginas HTML, imagens ou outros recursos.  
- O Apache é um dos servidores HTTP mais utilizados no mundo.  

---

## Passo a Passo

### 1. Instalar o Apache
No Linux (Ubuntu/Debian), execute no terminal:
```bash
sudo apt update
sudo apt install apache2 -y
````

Verifique se o serviço está rodando:

```bash
sudo systemctl status apache2
```

No Windows, pode-se instalar via **XAMPP** ou **WampServer**.

---

### 2. Criar o arquivo HTML

Edite ou crie um arquivo chamado `index.html` dentro da pasta padrão do Apache:

Linux (Ubuntu/Debian):

```bash
sudo nano /var/www/html/index.html
```

Windows (XAMPP/WAMP):
Salve o arquivo dentro da pasta `htdocs`.

---

### 3. Código HTML da Página

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Protocolos de Aplicação</title>
  <!-- Bootstrap CSS -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-dark text-white">

  <div class="container text-center py-5">
    <div class="card shadow-lg p-4 bg-gradient rounded-4" style="background: linear-gradient(135deg, #007bff, #6610f2);">
      <h1 class="display-4 fw-bold text-warning">Olá, seja bem-vindo!</h1>
      <p class="lead mt-3">
        Esta é a disciplina de <strong>Protocolos de Aplicação</strong>.
      </p>
      <p>
        Você está vendo, na prática, os conceitos discutidos em sala sobre o protocolo <strong>HTTP</strong> e servidores Web.
      </p>
      <a href="#" class="btn btn-lg btn-light mt-3">Explorar Mais</a>
    </div>
  </div>

  <!-- Bootstrap JS -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

---

### 4. Reiniciar o Apache

Após salvar o arquivo, reinicie o Apache:

```bash
sudo systemctl restart apache2
```

---

### 5. Acessar a página no navegador

* Abra o navegador e digite:

  ```
  http://localhost
  ```
* Ou, em outra máquina da mesma rede, use o **IP do servidor**:

  ```
  http://<IP_DO_SERVIDOR>
  ```

---

## O que observar

* O navegador envia uma **requisição HTTP GET** ao servidor Apache.
* O Apache responde com a **página HTML** criada.
* É possível inspecionar os cabeçalhos da requisição e resposta usando a aba **Ferramentas de Desenvolvedor → Rede (F12)**.

---

## Prova Prática:

**1.** Após criar a página `index.html` e acessar pelo navegador, abra as **Ferramentas de Desenvolvedor (F12 → Aba Rede)**.

* Capture o cabeçalho da **requisição HTTP** enviada ao servidor Apache.
* Identifique:

  * Método utilizado
  * Código de status da resposta
  * Tipo de conteúdo retornado

---

**2.** Modifique o arquivo `index.html` para incluir:

* Um botão que leve ao site do Apache:
  👉 [https://httpd.apache.org](https://httpd.apache.org)

Exemplo de código:

```html
<a href="https://httpd.apache.org" class="btn btn-success mt-3">Visitar o site do Apache</a>
```

---

**3.** Crie uma segunda página chamada `sobre.html` com o seguinte conteúdo:

```html
<h1>Sobre a Disciplina</h1>
<p>Esta disciplina ensina os conceitos e práticas sobre protocolos de aplicação na Internet.</p>
```

Adicione na `index.html` um botão que leve a essa nova página.

---

**4.** Reinicie o Apache e acesse a nova página via navegador:

```
http://localhost/sobre.html
```

**5.** Explique como o **servidor Apache** se comporta quando:

* A página requisitada **existe** no diretório `/var/www/html`.
* A página requisitada **não existe**.

> Dica: acesse um endereço inexistente, por exemplo:
>
> ```
> http://localhost/naoexiste.html
> ```
>
> e observe a resposta HTTP.