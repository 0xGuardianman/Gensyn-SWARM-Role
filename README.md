# 🤖 Gswarm Role & Telegram Bot Setup

Welcome!  
This guide will walk you through setting up the **Gswarm monitoring bot**, connecting it with **Telegram**, and linking it to **Discord** to earn **The Swarm role**.

Gswarm allows you to monitor your Gensyn swarm node’s activity directly from your phone using Telegram.

---

## 📘 Official Reference
🔗 **Docs:** [Deep-Commit / Gswarm](https://github.com/Deep-Commit/gswarm)

---

## ⚙️ Step 1 — Install Gswarm

Before anything else, make sure you have **Go (Golang)** installed and updated.

### 🧩 1. Install Go
Run the following commands to install Go 1.22.4:

```bash
sudo rm -rf /usr/local/go
curl -L https://go.dev/dl/go1.22.4.linux-amd64.tar.gz | sudo tar -xzf - -C /usr/local
echo 'export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin' >> $HOME/.bash_profile
echo 'export PATH=$PATH:$(go env GOPATH)/bin' >> $HOME/.bash_profile
source .bash_profile
go version
```

### 🧱 2. Install Gswarm
Once Go is installed, run this command to download and install the Gswarm tool:

```bash
go install github.com/Deep-Commit/gswarm/cmd/gswarm@latest
```

After installation, you can run **gswarm** from anywhere if your Go bin directory is in your PATH.

✅ **Check installation:**
```bash
gswarm --version
```

---

## 💬 Step 2 — Create and Configure Your Telegram Bot

You’ll need a Telegram bot that can communicate with your Gswarm instance.  
This process takes just a few minutes.

### 🪄 1. Create a New Bot
1. Open Telegram and start a chat with **[@BotFather](https://t.me/BotFather)**  
2. Type `/newbot`  
3. Follow the steps to name your bot and choose a username  
4. Copy the **bot token** provided — you’ll use it soon

### 🆔 2. Find Your Chat ID
1. Send any message to your new bot on Telegram  
2. Open this link in your browser (replace `<YOUR_BOT_TOKEN>` with your token):

```
https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getUpdates
```

3. You’ll see something like this:
   ```json
   "chat": { "id": 123456789 }
   ```
   That number is your **chat ID**.

💡 *If you get an empty result (`"result":[]`), send another message to your bot and refresh the link.*

---

## ⚙️ Step 3 — Start the Gswarm Bot

Now connect everything together.

Run this command:
```bash
gswarm
```

You’ll be asked for:
- Your **Telegram Bot Token**  
- Your **Chat ID**  
- Your **EOA Address** (available in your [Gensyn Dashboard](https://dashboard.gensyn.ai))

Once done, Gswarm will start sending live node updates to your Telegram chat.

---

## 🔗 Step 4 — Link Discord & Telegram

To earn *The Swarm* Discord role, you’ll need to link your Telegram and Discord accounts.

### 🧠 1. Get a Link Code
1. Open the official **Gensyn Discord**  
2. Go to the `#|swarm-link` channel  
3. Type:
   ```
   /link-telegram
   ```
4. You’ll receive a one-time **verification code**

### 💬 2. Verify in Telegram
1. Go back to your Telegram bot  
2. Send:
   ```
   /verify <code>
   ```
   *(Replace `<code>` with the code from Discord)*

✅ Once verified, your Discord and Telegram accounts will be linked — and you’ll receive **The Swarm Role** 🌀

---

## 🧩 Optional — Keep Gswarm Running in the Background

If you want the bot to stay active even when you close your terminal, use **screen**:

```bash
screen -S gswarm
gswarm
```

Detach the session:
```
Ctrl + A + D
```

To return later:
```bash
screen -r gswarm
```

---

## 🎉 You’re Done!

You’ve successfully:
- Installed **Gswarm**
- Created a **Telegram bot**
- Connected it to your **Gensyn node**
- Linked it with **Discord**
- Earned **The Swarm role**

---

**🚀 Monitor smarter. Stay connected. Join The Swarm. ⚡**
