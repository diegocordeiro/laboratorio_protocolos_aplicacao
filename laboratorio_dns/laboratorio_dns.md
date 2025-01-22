# **Laboratório Prático: Entendendo o Funcionamento do Protocolo DNS**

## **Objetivo**
Demonstrar, de forma prática, como o protocolo DNS (Domain Name System) converte nomes de domínio em endereços IP.

---

## **Materiais Necessários**
- Um computador ou laptop com acesso à internet.
- Terminal de comando (Linux, macOS ou Windows com CMD ou PowerShell).

---

## **Etapas do Laboratório**

### **1. O que é o DNS?**
Antes de começarmos, entenda:
- O DNS é como uma "agenda telefônica" da internet.
- Ele traduz nomes amigáveis (como `www.google.com`) para endereços IP que os computadores utilizam para se comunicar (como `142.250.64.78`).

---

### **2. Passo 1: Consultar um Nome de Domínio**
1. Abra o terminal em seu computador.
2. Execute o seguinte comando para consultar o DNS de um domínio:
   - No Windows (PowerShell ou CMD):  
     ```bash
     nslookup www.google.com
     ```
   - No Linux/macOS:  
     ```bash
     nslookup www.google.com
     ```

3. **Perguntas:**
   - Qual é o endereço IP retornado para o domínio `www.google.com`?
   - Observe se há servidores DNS mencionados. Qual é o nome do servidor usado?

---

### **3. Passo 2: Testando outro domínio**
1. Escolha outro domínio, como `www.ifpi.edu.br`, e execute o mesmo comando:
   ```bash
   nslookup www.ifpi.edu.br
   ```
2. **Perguntas:**
   - Qual é o endereço IP associado a este domínio?
   - Compare o tempo de resposta para diferentes domínios. Alguma diferença?

---


### **4. Passo 3: Analisando as Etapas do DNS**
1. Explore as etapas de resolução de DNS utilizando o comando `tracert` ou `traceroute`:
   - No Windows:
     ```bash
     tracert www.ifpi.edu.br
     ```
   - No Linux/macOS:
     ```bash
     traceroute www.ifpi.edu.br
     ```

2. **Perguntas:**
   - Quantos "saltos" (hops) você observou?
   - Qual foi o tempo médio de resposta?

---

## **Conclusão**
- Agora você sabe como o DNS funciona na prática!
- Pense em como seria difícil acessar sites sem esse protocolo.

---

## **Extras (Opcional)**
- Descubra o endereço IP do seu próprio computador usando o comando:
  - Windows:
    ```bash
    ipconfig
    ```
  - Linux/macOS:
    ```bash
    ifconfig
    ```
- Pesquise como o cache DNS do seu computador influencia a navegação.