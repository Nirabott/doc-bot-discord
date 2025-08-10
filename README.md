# 🤖 Guia Completo de Bots do Discord

[![Discord](https://img.shields.io/badge/Discord-Bots-5865F2?logo=discord&logoColor=white)](https://discord.com/developers/applications)
[![Node.js](https://img.shields.io/badge/Node.js-v16%2B-green?logo=node.js)](https://nodejs.org/)
[![License](https://img.shields.io/badge/license-MIT-orange)](LICENSE)

Este repositório é um **guia prático** sobre **bots do Discord**, explicando **o que são**, **como funcionam** e **como criar o seu próprio bot**.  
Perfeito para iniciantes ou desenvolvedores que querem entender como essa tecnologia funciona.

---

## 📌 O que é um Bot do Discord?
Um **bot do Discord** é um programa automatizado que interage com usuários e servidores através da API do Discord.  
Eles podem executar várias funções:
- Moderar chats (banir, silenciar, excluir mensagens)
- Reproduzir música
- Buscar informações na internet
- Criar sistemas de tickets, economia e ranking
- Automatizar tarefas repetitivas

---

## ⚙️ Como um Bot do Discord Funciona?
- O bot se conecta à **API do Discord** usando um **token de autenticação**
- Ele **ouve eventos** (mensagens enviadas, membros entrando, etc.)
- Ele **responde** com base em regras ou comandos programados
- Pode interagir com **APIs externas** para buscar ou enviar dados

---

## 🛠 Ferramentas e Tecnologias
Para criar bots, as linguagens e bibliotecas mais usadas são:
- **JavaScript / Node.js** → [discord.js](https://discord.js.org/)
- **Python** → [discord.py](https://discordpy.readthedocs.io/en/stable/)
- **Java** → [JDA](https://github.com/discord-jda/JDA)
- **.NET / C#** → [DSharpPlus](https://github.com/DSharpPlus/DSharpPlus)

---

## 🚀 Criando um Bot do Zero
1. **Criar um aplicativo no Discord Developer Portal**
   - Acesse [Discord Developer Portal](https://discord.com/developers/applications)
   - Clique em **"New Application"** e dê um nome ao bot
2. **Gerar o token**
   - Vá em **"Bot" → "Add Bot"**
   - Copie o **Token** (⚠️ mantenha-o privado)
3. **Convidar o bot para seu servidor**
   - Vá em **OAuth2 → URL Generator**
   - Marque **bot** e as permissões necessárias
   - Use o link gerado para adicioná-lo ao servidor
4. **Programar o bot**
   - Escolha sua linguagem e biblioteca
   - Conecte usando o token
   - Adicione eventos e comandos
5. **Hospedar**
   - Pode ser localmente ou em serviços como:
     - [Railway](https://railway.app/)
     - [Replit](https://replit.com/)
     - [Heroku](https://heroku.com/)
     - [VPS / Servidores dedicados](https://www.vultr.com/)

---

## 📄 Exemplo simples em Node.js
```js
const { Client, GatewayIntentBits } = require('discord.js');
const client = new Client({ intents: [GatewayIntentBits.Guilds, GatewayIntentBits.GuildMessages, GatewayIntentBits.MessageContent] });

client.once('ready', () => {
    console.log(`Bot logado como ${client.user.tag}`);
});

client.on('messageCreate', message => {
    if (message.content === '!ping') {
        message.channel.send('Pong!');
    }
});

client.login('SEU_TOKEN_AQUI');
