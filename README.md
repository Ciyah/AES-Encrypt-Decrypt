# AES-Encrypt-Decrypt 🔐
> A Python CLI tool for secure file encryption/decryption using AES-256-GCM, PBKDF2, and a random salt.

---

## 💡 About This Project
This is a command-line utility for secure file encryption and decryption. This project demonstrates how to properly implement modern, applied cryptography in Python, using industry-standard practices to protect against common attacks and ensure both **confidentiality** and **data integrity**.

---

## ✨ Key Features
* **🔒 AES-256-GCM Mode:** Uses an Authenticated Encryption with Associated Data (AEAD) cipher. This not only encrypts the data but also creates an **authentication tag**. If the data is tampered with (even by one bit) or the key is wrong, decryption will fail.
* **🔑 Strong Key Derivation (PBKDF2):** Never uses the password directly as the key. It uses PBKDF2 (Password-Based Key Derivation Function 2) with 100,000 iterations to "stretch" the password into a robust 256-bit cryptographic key.
* **🧂 Random Salt:** A unique, 16-byte salt is generated for every encryption. This protects against rainbow table attacks and ensures that encrypting the same file with the same password will result in a different ciphertext every time.
* **🤫 Secure Password Entry:** Uses the `getpass` module to securely prompt for a password, so it isn't shown on the screen or stored in your shell history.
* **🖥️ User-Friendly CLI:** Built with `argparse` to provide clear `encrypt` and `decrypt` sub-commands.

---

## 🛠️ Tech Stack
* **🐍 Python 3**
* **🛡️ `pycryptodome`:** The core library for cryptographic operations (AES, PBKDF2).
* **⌨️ `argparse`:** For building the command-line interface.
* **🤫 `getpass`:** For secure password input.

---

## 📸 Demo
Here is a step-by-step example of the script in action.

### 1. The Original File (`message.txt`)
First, we start with a simple text file containing a secret message.

<img width="363" height="138" alt="image" src="https://github.com/user-attachments/assets/a5d937b5-6de1-4755-af69-67375d2bd54a" />


---
### 2. Running the Encrypt Command
Next, we run the `encrypt` command in the terminal. It securely prompts for a password (which is hidden as you type).

<img width="1185" height="72" alt="image" src="https://github.com/user-attachments/assets/2c56ef55-7a2c-45ba-9114-1113d2f08a1c" />
Example the Password  i have used is Ciyah123


---
### 3. The Encrypted File (`encrypted.bin`)
The script produces a `.bin` file. The data is now unreadable, authenticated ciphertext.

<img width="450" height="179" alt="image" src="https://github.com/user-attachments/assets/5b240325-2898-459c-982b-0a1c56bc48eb" />


---
### 4. Running the Decrypt Command
We run the `decrypt` command, using the same password.

<img width="1202" height="65" alt="image" src="https://github.com/user-attachments/assets/76ce8ccf-c7a4-46a5-95fc-7def529de0e3" />


---
### 5. The Final Decrypted File (`decrypted.txt`)
The script successfully decrypts the file, and the content is identical to the original.

<img width="363" height="137" alt="image" src="https://github.com/user-attachments/assets/d88fc389-5540-43fc-847c-df9eb2d625ca" />


---
### 6. Security Check (Failed Decryption)
Here is what happens if you use the **wrong password**. The script instantly fails and protects the data, proving the authentication is working.

<img width="1196" height="68" alt="image" src="https://github.com/user-attachments/assets/b037819b-60a3-4596-b3c1-f97fafbd9bf8" />

## 🚀 How to Use

### 1. Installation
Install the required library:
```bash
python -m pip install pycryptodome
