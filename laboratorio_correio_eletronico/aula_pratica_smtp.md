# Prática SMTP

## Instalar as ferramentas necessárias:

```bash
sudo apt update
sudo apt install telnet mailutils -y
sudo apt install openssl -y
```

---

## Login com SSL no Google:

```bash
openssl s_client -connect smtp.gmail.com:587 -starttls smtp -tls1_3 -ign_eof
```

---

## Iniciando a conversação com o servidor:

```bash
EHLO localhost
```

---

## Autenticando usuário:

1. **Acesse sua Conta do Google**:  
   Faça login em [myaccount.google.com](https://myaccount.google.com).

2. **Navegue até a seção de segurança**:  
   No menu de navegação, selecione "Segurança".

3. **Verificação em duas etapas**:  
   Certifique-se de que a verificação em duas etapas está ativada. Se não estiver, ative-a seguindo as instruções fornecidas pelo Google.

4. **Gerar senha de app**:  
   Após ativar a verificação em duas etapas, na seção "Segurança", localize a opção "Senhas de app" e selecione-a.  
   Acesse [https://myaccount.google.com](https://myaccount.google.com) para mais detalhes.  
   Siga as instruções para gerar uma nova senha de app específica para o uso desejado.

---

## Gerar autenticação em Base64:

```bash
echo -n "usuario" | base64  # Anote o resultado
echo -n "senha app google" | base64    # Anote o resultado
```

- Digite no terminal:  
  ```bash
  AUTH LOGIN #inicia processo de login
  ```
- Ao receber a resposta `VXNlcm5hbWU6`, informe o usuário gerado acima.  
- Ao receber a resposta `UGFzc3dvcmQ6`, informe a senha gerada acima.  
- Se tudo estiver correto, o retorno será:  
  ```bash
  235 2.7.0 Accepted
  ```

---

## Envio do E-mail:

```bash
MAIL FROM:<seuemail@gmail.com>   # Indicar origem
RCPT TO:<destinatario@gmail.com> # Indicar destino
DATA                            # Iniciar o bloco do corpo do e-mail
Subject: Teste email

This is a test mailing
.

QUIT                            # Finalizar o bloco
```

---

## Outra forma de realizar o teste e ver a interação entre os servidores:

### Instalar cliente SMTP swaks:

No Ubuntu:

```bash
sudo apt install swaks
```

### Executar comando no terminal:

```bash
swaks --to destinatario@ifpi.edu.br --from remetente@ifpi.edu.br \
  --server smtp.gmail.com --port 587 --auth LOGIN \
  --auth-user remetente@ifpi.edu.br --auth-password "sua senha gerada no app google" --tls
```