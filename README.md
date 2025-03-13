# 🚀 EVM Drain - Emergency Drain

Welcome to the `evm-drain` repository! This repository script is designed for monitoring incoming deposit multiple Chain wallets (Eth, BSC, Pol etc), checking their balances, and automatically withdrawing funds to a vault wallet when has available balance. It uses WebSockets for real-time updates.

---

## 📌 Features

- 📡 **Emergency Fund Transfer:** Quickly move assets from compromised wallets.
- 🔄 **Multi-Network Support:** Works with EVM-compatible blockchains. 
- 🎯 **Command-Line Interface:** Simple usage via terminal. 
- 🚀 **WebSocket Monitoring:** Real-time updates on wallet balances. 
- 🔒 **Auto Withdrawal:** Sends funds automatically if have balance. 

---

## 📦 Installation

### **1️⃣ Install Node.js & Dependencies**
Ensure Node.js is installed 

Clone the repository:

```sh
git clone https://github.com/kidd142/evm-drain.git
cd evm-drain
```

Install required packages:

```sh
npm install dotenv ethers readline crypto
```

---

### **2️⃣ Set Up Environment Variables**
Create a `.env` file in the same directory and add:

```ini
VAULT_WALLET_ADDRESS=0x000xxx                           #TargetAddress
CONFIRMATIONS_BEFORE_WITHDRAWAL=2                       #WaitingConfirmation
RPC_WEBSOCKET_URLS=wss://rpc1 wss://rpc2 wss://rpc3     #RPCURL (Seperate Space)

DEPOSIT_WALLETS_PRIVATE_KEYS="
0x0001
0x0002
0x0003
"                                                       #PrivateKeys (Seperate Line)
```

Replace with actual values.

---

## 🚀 Usage

### **3️⃣ Run the Script**
```sh
node index.js
```
You'll be prompted to enter an **Access Key**.

```
🔐 Enter Access Key: ██████████████████████████
✅ Access Key Accepted! Starting wallet monitoring...
```

---

### **4️⃣ Enter Access Key**
When prompted, enter a **64-character access key** to start wallet monitoring.


---
📢 **Need access key? Contact me on Telegram:** [@kidd142](https://t.me/kidd142)

---

### **5️⃣ Wallet Monitoring & Auto Withdrawals**
The script:
  - Checks wallet balances.
  - Countiously run 24/7.
  - If has enough balance, it sends the remaining amount to `VAULT_WALLET_ADDRESS`.
  - Displays transaction history.

```
🔄 Wallet Balances:
💰 0xabc123...def456: 0.032 ETH
💰 0x987654...321abc: 0.050 ETH

📜 Last 3 Transactions:
➤ [2025-03-12 10:30:00] 0xabc123...def456 → Vault | Tx: 0xfa12b3...8c7d
➤ [2025-03-12 10:32:00] 0x987654...321abc → Vault | Tx: 0xe98a1b...d47c
```

---

### **6️⃣ Automatic WebSocket Reconnection**
If a WebSocket disconnects, the script:
- Waits 10 seconds before trying to reconnect.
- Retries every 30 seconds if reconnection fails.

```
⚠️ WebSocket disconnected: wss://rpc.url
🔄 Attempting to reconnect in 10 seconds...
✅ Reconnected successfully!
```

---

### **7️⃣ Stop the Script**
Press `Ctrl + C` to stop the script.

```
🛑 Stopping wallet monitoring...
✅ Process terminated.
```

---

## 🛠 Troubleshooting
- ❌ **Missing Environment Variables**: Ensure `.env` contains valid values.
- ❌ **Access Key Issues**: Check if the entered key is 64 characters long.
- ❌ **WebSocket Errors**: Ensure the WebSocket URL is correct and active.
- ❌ **Insufficient Funds Error**: Ensure wallets have enough ETH to cover gas fees.

---
### Contribution

Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

## Donations
---

If you would like to support the development of this project, you can make a donation using the following addresses:

- **Solana**: `EtgVgPvN6Z35551w7znEJ22mvHDmGpY9nHwQwWtgdQZ6`
- **EVM**: `0xb150b7f241979c89fabb9bf333ffd86b8e2e34d4`
- **BTC**: `bc1pp5r2sn8k3ryjdc48p7lmuhjmsep489ac89lhl7z8pg65jmzf9pusk6hsd8`
---
## 📜 License
This project is for educational purposes only. Use at your own risk. ⚠️
