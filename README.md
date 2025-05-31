# 🔐 Blockchain-Based Cloud File Sharing System

A decentralized file-sharing application built using **Solidity** smart contracts and **IPFS**. This project demonstrates secure, tamper-proof file storage by storing file hashes on the Ethereum blockchain. It integrates with **MetaMask** for user authentication and **IPFS** for decentralized file hosting.

---

## 🧰 Tech Stack

- **Smart Contracts:** Solidity (tested via Hardhat or Remix IDE)
- **Storage:** IPFS (InterPlanetary File System)
- **Wallet:** MetaMask
- **Frontend:** HTML, CSS, JavaScript (no Node.js)

---

## 📁 Features

- 🔒 **Decentralized file storage** using IPFS
- 📬 **File hash stored on Ethereum** via smart contract
- 🦊 **MetaMask integration** for secure user access
- 🧾 **Simple UI** to upload and record files
- 🛡️ Ensures **data integrity** and **immutability**

---

## 📂 Project Structure

blockchain-file-sharing/
├── contracts/
│ └── FileShare.sol # Smart contract
├── scripts/
│ └── deploy.js # Contract deployment using Hardhat (optional)
├── frontend/
│ ├── index.html
│ ├── script.js
│ └── style.css



---

## 🛠️ Getting Started

### 1. MetaMask Setup

- Install [MetaMask](https://metamask.io/) in your browser
- Create or import a wallet
- Switch to a local or test Ethereum network (e.g., Goerli)

### 2. Upload Smart Contract

Use [Remix IDE](https://remix.ethereum.org/) or Hardhat to:

- Compile `FileShare.sol`
- Deploy it to your desired network
- Save the deployed contract address and ABI

### 3. Frontend Setup

Update `script.js` with:

- Your contract ABI
- Contract address
- IPFS upload endpoint (e.g., using [Infura](https://infura.io/))

Then simply open `index.html` in your browser.

---

## 🔁 Example Usage Flow

1. User uploads a file via frontend
2. File is stored on IPFS → returns a unique CID
3. CID is sent to Ethereum smart contract via MetaMask
4. Smart contract stores the CID under user's account

---

## ✨ Sample Smart Contract

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract FileShare {
    mapping(address => string[]) public userFiles;

    function uploadFile(string memory ipfsHash) public {
        userFiles[msg.sender].push(ipfsHash);
    }

    function getFiles(address user) public view returns (string[] memory) {
        return userFiles[user];
    }
}


# Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a script that deploys that contract.

Try running some of the following tasks:

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat run scripts/deploy.js
```
