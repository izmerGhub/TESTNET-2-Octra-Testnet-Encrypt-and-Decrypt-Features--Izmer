

# 🧪 TESTNET TASK 2: Octra Testnet Encrypt and Decrypt Features


This guide covers the **private transaction features** in the Octra Testnet client. These features allow you to manage your OCT token privacy using encryption-based mechanisms.

## 🔑 Feature Definitions

- **Encrypt Balance** – Hide (shield) your OCT from the public ledger, moving it to a private state.
- **Private Transfer** – Send OCT privately to another address without exposing the amount or recipient.
- **Claim Transfers** – Accept incoming private transfers into your encrypted balance.
- **Decrypt Balance** – Reveal previously shielded OCT and return it to the public ledger.

### 🧪 PREVIOUSLY Octra Testnet Task 1: Wallet and Token Setup

#### 📥 Don't have an Octra wallet yet?  
👉 [CLICK HERE](https://github.com/octra-labs/wallet-gen) to create your wallet using the official wallet generator.

#### 💧 Need Octra testnet tokens?  
👉 [CLICK HERE](https://faucet.octra.network/) to claim from the official faucet.


---

### Install Dependencies (Linux base)

#### Install & Update Packages:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev -y
```

#### Install Node.js (For VPS Users):
```bash
sudo apt update
sudo curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
node -v
npm install -g yarn
yarn -v
```
### Install Dependencies (MacOs base)

Ensure you have these tools installed on your **macOS** system:

```bash
xcode-select --install   # Install essential developer tools (if not already)
brew update
brew install git python3 node jq wget tmux nano lz4 libtool autoconf automake pkg-config openssl
```

## ⚠️ Important: Backup Wallet Before Proceeding

If you used the previous Octra client for **Testnet Task 1**, **make sure to backup your wallet details now** (e.g., `wallet.json`, private keys, addresses) before deleting any files or folders. Losing these means losing access to your funds and testnet state.

---

## 🔄 Update to Latest Octra Testnet CLI

### A. Remove old client folder (optional but recommended)
```bash
rm -rf octra_pre_client
```

### B. Clone latest Octra client repository
```bash
git clone https://github.com/octra-labs/octra_pre_client.git
cd octra_pre_client
```

### C. Setup Python virtual environment and dependencies
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### D. Prepare wallet configuration
```bash
cp wallet.json.example wallet.json
nano wallet.json
```
Replace "private-key-here" with your Base64 encoded private key.  
Replace "octxxxxxxxx..." with your Octra testnet address starting with `oct`.  
Save and exit the editor.

### E. Run the node/client
```bash
./run.sh
```
This starts the Octra testnet client with your wallet and latest features.

✅ You are now set with the latest Octra CLI to proceed with Testnet Task 2: Encrypt, Private Transfer, Claim, and Decrypt.

## 🔐 1. Encrypt Balance (Make It Private)

Move your tokens from the public ledger into an encrypted (shielded) balance.

### 🖥️ What You See:
```
public balance:   84.213312 oct
encrypted:        20.800000 oct
total:            105.013312 oct

max encryptable: 83.213312 oct

amount to encrypt: 1
encrypt 1.000000 oct? [y/n]:
```

### ✅ Steps:
1. Enter an amount (up to `max encryptable`).
2. Confirm with `y`.

📦 Your OCT is now **private** and ready for confidential transfers.

---

## ✉️ 2. Private Transfer (Send Privately)

Send tokens to another address **without revealing the details on-chain**.

### 🖥️ What You See:
```
encrypted balance: 19.800000 oct

recipient address:
<<<<<<< HEAD
oct5VXSG3UmtQwgvVzhs6ojpwmvoFmDihyRoDrXLcR4h4bY
=======
octEWCSTAxhDF8TB3EUudhpYv9MpQuihcVZzfh1RgHJ1xdy
>>>>>>> d899f79 (Save latest changes before deleting codespace)

recipient balance: 157.372731

amount: 1

send 1.000000 oct privately to
<<<<<<< HEAD
oct5VXSG3UmtQwgvVzhs6ojpwmvoFmDihyRoDrXLcR4h4bY
=======
octEWCSTAxhDF8TB3EUudhpYv9MpQuihcVZzfh1RgHJ1xdy
>>>>>>> d899f79 (Save latest changes before deleting codespace)

[y]es / [n]o:
```

### ✅ Steps:
1. Paste the recipient's Octra address.
2. Enter the amount to send.
3. Confirm with `y`.

📦 The private transfer is now pending and must be **claimed** by the receiver.

---

## 📥 3. Claim Private Transfers

Claim funds that were sent to you **privately**.

### 🖥️ What You See:
```
claim private transfers ─────────────────────────────────────────────

found 1 claimable transfers:

#   FROM                AMOUNT         EPOCH   ID
───────────────────────────────────────────────────────────────
[1] oct2HCHuG2Z3oE5oo...  0.100000 OCT    ep14369   #769

enter number to claim (0 to cancel):
```

### ✅ Steps:
1. Type the number of the transfer you want to claim (e.g., `1`).
2. Press Enter to confirm.

📦 The tokens are now added to your **encrypted balance**.

---

## 🔓 4. Decrypt Balance (Make It Public Again)

Unshield your private OCT and return it to the public ledger.

### 🖥️ What You See:
```
public balance:   84.213312 oct
encrypted:        19.800000 oct
total:            104.013310 oct

max decryptable: 19.800000 oct

amount to decrypt: 1
decrypt 1.000000 oct? [y/n]:
```

### ✅ Steps:
1. Enter the amount you want to decrypt (up to `max decryptable`).
2. Type `y` and press Enter.

📦 That amount is now visible on-chain and part of your public balance.

---

## 🧠 Feature Summary

| Feature             | Description |
|---------------------|-------------|
| 🔐 Encrypt Balance   | Move OCT into a private (shielded) balance |
| ✉️ Private Transfer  | Send tokens privately with no on-chain exposure |
| 📥 Claim Transfers   | Receive private transfers into your shielded balance |
| 🔓 Decrypt Balance   | Reveal private OCT and make it public again |

---

> ✅ You are now fully equipped to handle **private OCTRA transactions** on the testnet.  
> 💬 For issues, contact the Octra community or file an issue in this repo.
