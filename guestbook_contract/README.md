# 📦 Guestbook Contract (Move Backend)

This folder contains the **Move smart contract** that powers the Guestbook dApp on the Sui blockchain.  
It defines the `GuestBook` shared object and functions to create and post messages.

---

## 🛠️ Contract Overview

- **Module:** `guestbook_contract`
- **Structs:**
  - `Message` → stores sender, content, and timestamp.
  - `GuestBook` → stores a list of messages, count, and creation time.
- **Functions:**
  - `init` → initializes a new GuestBook shared object.
  - `create_message` → creates a message object (validates length).
  - `post_message` → posts a message to the GuestBook.
  - `get_message_count` → returns number of messages.

---

## ⚙️ Prerequisites

- [Sui CLI](https://docs.sui.io/guides/developer/getting-started/sui-install)  
- [Rust toolchain](https://www.rust-lang.org/tools/install) (if building from source)  
- Testnet SUI tokens → [Get from Faucet](https://faucet.sui.io/)  

---

## 🔹 Build & Test

Run tests locally with:

```bash
sui move build
sui move test
```

---

## 🚀 Deploy to Testnet

Publish the contract:

```bash
sui client publish --gas-budget 20000000
```

When publishing, note the following IDs from the output:
- **Package ID** → the deployed smart contract package
- **GuestBook Object ID** → the shared GuestBook object created on-chain

Example:
```
PackageID: 0x9f4afc...
GuestBook ID: 0x8ccd8f...
```

---

## 🔎 Verify On-Chain

Check GuestBook object after posting a message:

```bash
sui client object <GUESTBOOK_OBJECT_ID>
```

You should see stored messages and message count.

---

## 📚 Resources
- [Move Language](https://github.com/move-language/move)
- [Sui Move Examples](https://docs.sui.io/guides/developer/move)
