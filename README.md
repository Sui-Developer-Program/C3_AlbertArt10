# 📝 Sui Guestbook dApp

A full-stack decentralized application built on the **Sui blockchain**.  
It allows users to post short guestbook messages (up to 100 characters) that are stored permanently on-chain.  

The project is split into two parts:
- **`guestbook_contract/`** → Move smart contract (backend, on-chain logic).
- **`guestbook_dapp/`** → Next.js frontend (UI + Enoki integration).

---

## 📂 Project Structure

```
guestbook/
│
├── guestbook_contract/   # Move smart contract (backend)
│
├── guestbook_dapp/       # Next.js frontend (UI for interacting with contract)

```

---

## 🚀 Features

- ✍️ Post messages (up to 100 chars).  
- 💾 Messages stored **permanently** on Sui blockchain.  
- ⛽ Gas-free transactions sponsored by **Enoki**.  
- 🌐 Simple Next.js UI to interact with the contract.  

---

## ⚙️ Prerequisites

Make sure you have installed:
- [Node.js 18+](https://nodejs.org/)
- [Sui CLI](https://docs.sui.io/guides/developer/getting-started/sui-install)
- [Git](https://git-scm.com/)
- [Testnet SUI tokens](https://faucet.sui.io/)
- [Enoki](https://docs.sui.io/tools/enoki) account & API keys (for sponsored transactions)

---

## 🛠️ Setup & Run

### 1. Clone the repo
```bash
git clone <your-repo-url>
cd guestbook
```

### 2. Setup backend (smart contract)
```bash
cd guestbook_contract
sui move test
sui client publish --gas-budget 20000000
```
⚡ Note down the **Package ID** and **GuestBook Object ID**.

### 3. Setup frontend (UI)
```bash
cd ../guestbook_dapp
```

Update `.env.local` with your values:
```ini
NEXT_PUBLIC_PACKAGE_ID=<YOUR_PACKAGE_ID>
NEXT_PUBLIC_GUESTBOOK_ID=<YOUR_GUESTBOOK_OBJECT_ID>
ENOKI_SECRET_KEY=<YOUR_ENOKI_SECRET_KEY>
```

Install dependencies and run:
```bash
npm install
npm run dev
```

Open → [http://localhost:3000](http://localhost:3000)

---

## 📚 Documentation

- [guestbook_contract/README.md](./guestbook_contract/README.md) – backend smart contract setup  
- [guestbook_dapp/README.md](./guestbook_dapp/README.md) – frontend dApp setup  

---

## 📝 Example

- Post a message via dApp:  
  ```
  First message on my Sui Guestbook 🎉
  ```
- Verify on-chain:  
  ```bash
  sui client object <GUESTBOOK_OBJECT_ID>
  ```

---

## 📖 Resources
- [Sui Official Docs](https://docs.sui.io/)
- [Move Language](https://github.com/move-language/move)
- [Enoki Sponsored Transactions](https://docs.sui.io/tools/enoki)
