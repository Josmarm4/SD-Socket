# Comunicação entre Processos: Socket (Versão Segura: SSL)

## Descrição do Projeto

Este projeto implementa um aplicativo cliente-servidor simples utilizando sockets para comunicação. O servidor aceita conexões em uma porta específica (5050) e permite troca de mensagens entre cliente e servidor. O cliente se conecta ao servidor para enviar e receber mensagens.

---

## Funcionalidades

- **Servidor**:
  - Escuta conexões na porta 5050.
  - Processa mensagens de um cliente por vez.
  - Permite troca de mensagens entre cliente e servidor.
- **Cliente**:
  - Conecta-se ao servidor na porta 5050.
  - Envia mensagens e processa respostas do servidor.

---

## Importações das Classes

- `java.io` - Para manipulação de fluxos de entrada e saída.
- `java.net` - Para funcionalidades de rede, incluindo sockets.
- `java.util` - Para leitura de entrada do usuário (Scanner).

---

## Estrutura do Código

### Classe `Servidor`
- **Variáveis**:
  - `ServerSocket server` - Escuta conexões na porta 5050.
  - `Socket connection` - Representa a conexão com um cliente.
  - `ObjectOutputStream output` - Para enviar mensagens ao cliente.
  - `ObjectInputStream input` - Para receber mensagens do cliente.
- **Método `runServer`**:
  1. Cria o `ServerSocket`.
  2. Aguarda e aceita conexões de clientes.
  3. Processa mensagens recebidas até que o cliente envie "CLIENT>>> sair".

### Classe `Cliente`
- **Variáveis**:
  - `Socket client` - Representa a conexão com o servidor.
  - `ObjectOutputStream output` - Para enviar mensagens ao servidor.
  - `ObjectInputStream input` - Para receber mensagens do servidor.
  - `String message` - Armazena a mensagem a ser enviada ou recebida.
- **Método `runClient`**:
  1. Conecta-se ao servidor no `localhost:5050`.
  2. Envia mensagens para o servidor.
  3. Processa respostas até que o usuário digite "CLIENT>>> sair".

---

## Como Executar

1. **Clone este repositório**:
   ```bash
   git clone https://github.com/Josmarm4/SD-Socket.git
   ```
2. **Compilação:**
    - Compile as classes do servidor e cliente utilizando o comando javac:
   ```bash
    javac Servidor.java
    javac Cliente.java
   ```
3. **Execução:

- Iniciar o servidor: Abra uma janela de terminal e execute o servidor:
```bash
    java Servidor
```
- Iniciar o cliente: Abra outra janela de terminal e execute o cliente:
```bash
    java Cliente
```
4. Interação Cliente-Servidor:
## Envie as seguintes mensagems:
* CLIENT>>> olá
* SERVER>>> olá, tudo bem?
* CLIENT>>> tudo certo! vou sair da conversa ok?
* SERVER>>> ok
* CLIENT>>> sair
* SERVER>>> ok
* CLIENT>>> sair
* SERVER>>> sair