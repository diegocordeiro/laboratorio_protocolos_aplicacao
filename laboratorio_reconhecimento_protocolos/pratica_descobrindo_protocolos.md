## 💻 Atividade Prática — Descobrindo os Protocolos em Ação com Wireshark

### 🎯 Objetivo
Observar em tempo real os protocolos da camada de aplicação funcionando no computador, utilizando o analisador de pacotes **Wireshark**.

---

### 🧰 Materiais Necessários
- Computador com acesso à internet
- Wireshark instalado ([Download aqui](https://www.wireshark.org/))
- Navegador web (Firefox, Chrome, etc.)

---

### 🔧 Passo a Passo

1. **Abrir o Wireshark**
   - Clique no ícone do Wireshark.
   - Selecione a interface de rede correta (geralmente `Wi-Fi` ou `Ethernet`).

2. **Iniciar a captura**
   - Clique no botão **Start Capturing Packets** (ícone do tubarão).

3. **Acessar um site no navegador**
   - Exemplo: `https://aulas-diegocordeiro.duckdns.org`
   - Tente também: `http://example.com`

4. **Aplicar filtros no Wireshark**
   Use os filtros abaixo para visualizar os protocolos específicos:
   - `http` → para ver pacotes HTTP
   - `dns` → para ver requisições DNS
   - `tcp.port == 443` → para conexões HTTPS

5. **Explorar os pacotes capturados**
   - Observe a coluna "Protocol" e encontre:
     - HTTP
     - DNS
     - TLS/HTTPS
   - Clique em um pacote para ver os detalhes no painel inferior

6. **Responder e discutir**
   - Qual protocolo aparece antes: DNS ou HTTP?
   - Qual a diferença entre HTTP e HTTPS?
   - O que você observou na comunicação cliente-servidor?

---

### ✍️ Atividade
| Item observado: XXXX | Protocolo: YYY | Porta padrão: ZZZ | Observações: |

---
