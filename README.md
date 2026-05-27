# 🛡️ CipherChat (SecureConnect)

> **A Secure, Multi-Client, End-to-End Encrypted Communication System.**

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Security](https://img.shields.io/badge/Security-AES--256_Encryption-brightgreen?style=for-the-badge)
![Networking](https://img.shields.io/badge/Networking-TCP_Sockets-blue?style=for-the-badge)

## 📖 Overview

**CipherChat** is a robust desktop messaging application designed to demonstrate the core principles of Network Security and Cryptography. Unlike traditional chat applications where the server can read or log your messages, CipherChat strictly employs a **Zero-Knowledge Architecture**. 

Messages are encrypted locally on your device (the Client) using advanced AES-256 encryption and are only decrypted upon reaching the intended receiver's device. The central server acts merely as a blind postman routing encrypted bytes, ensuring total privacy and data confidentiality.

---

## 🚀 Key Features

### 🔒 Security Features
* **End-to-End Encryption (E2EE):** Utilizes AES (Fernet) to encrypt all messages before they ever leave your device.
* **Data Integrity:** Implements HMAC-SHA256 signatures to actively detect any tampering or packet manipulation during transit.
* **Secure Authentication:** Employs PBKDF2 (Password-Based Key Derivation Function) to generate cryptographically strong 32-byte keys from a simple Room Password.
* **Zero-Knowledge Server:** The server architecture routes raw encrypted bytes without ever having access to the decryption keys or plain-text data.

### 💻 Application Features
* **Multi-Client Support:** Facilitates real-time group chatting and broadcasting over a Local Area Network (LAN).
* **Modern GUI:** Built with `CustomTkinter` to provide a sleek, professional Dark Mode user experience.
* **Hacker View / Developer Mode:** Features a dedicated UI toggle that reveals the raw ciphertext (e.g., `gAAAA...`) to visually demonstrate the active encryption process.
* **Live Status Indicators:** Provides real-time visual feedback for network connection and authentication status.

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Language** | Python 3.10+ | Core Application Logic |
| **GUI Framework** | CustomTkinter | Modern User Interface |
| **Networking** | Python `socket` (TCP) | Reliable Data Transmission |
| **Concurrency** | `threading` | Handling UI and Network simultaneously |
| **Cryptography** | `cryptography.fernet` | Symmetric Encryption (AES) |
| **Key Derivation**| `PBKDF2HMAC` | Generating Strong Keys from Passwords |

---

## 📂 Project Structure

```text
CipherChat/
│
├── server/
│   ├── server.py           # The Central Hub (Run this first)
│   └── server_config.py    # IP/Port Configuration
│
├── client/
│   ├── client.py           # Entry point for the User App
│   ├── gui.py              # User Interface Logic
│   ├── encryption.py       # AES & Key Management Logic
│   └── network.py          # Socket Communication Handler
│
├── common/
│   ├── constants.py        # Shared Settings (Port, Headers)
│   └── crypto_utils.py     # Shared Math (Key Generation)
│
├── requirements.txt        # List of dependencies
└── README.md               # Documentation

## 📌 How to Run

**1. Install Dependencies:**
```bash
pip install -r requirements.txt

**2. Start the Server:**
Navigate to the server directory and run the central hub first.

```Bash
cd server
python server.py

**3. Launch the Client(s):**
Open a new terminal, navigate to the client directory, and start the application. You can run multiple instances of this to test multi-client chatting.

```Bash
cd client
python client.py
