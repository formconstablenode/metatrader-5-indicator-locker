# Metatrader 5 Indicator Locker

![Header](https://capsule-render.vercel.app/api?type=waving&color=0:0F0C29,100:302B63&height=220&section=header&text=Metatrader%205%20Indicator%20Locker&fontSize=55&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=Protect%20Your%20Proprietary%20Trading%20Algorithms&descAlignY=55&descSize=20)

<div align="center">

![Version](https://img.shields.io/badge/version-3.1.0-302B63?style=for-the-badge&logo=git&logoColor=white)
![Downloads](https://img.shields.io/badge/downloads-92.8K-0F0C29?style=for-the-badge&logo=download&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-FFD700?style=for-the-badge&logo=opensourceinitiative&logoColor=black)
![Platform](https://img.shields.io/badge/platform-windows%20%7C%20mt5-00C9FF?style=for-the-badge&logo=windows&logoColor=black)

</div>

---

## 🔒 The Ultimate Defense For Your Trading Edge

In the competitive world of algorithmic trading, your custom indicators and Expert Advisors (EAs) are your intellectual property. They represent months of research, backtesting, and fine-tuning. However, MetaTrader 5 (MT5) natively distributes `.ex5` files that can be easily decompiled by malicious actors. If your algorithm falls into the wrong hands, your edge is gone.

**Metatrader 5 Indicator Locker** is a specialized, open-source security toolkit designed to obfuscate and protect your MT5 source code before compilation. It is not just a simple wrapper; it is a multi-layered encryption and licensing framework that ensures your trading logic remains exclusively yours.

This repository provides a complete pipeline for securing your indicators. It includes a source code obfuscator, a hardware-locked licensing system, and a remote kill-switch mechanism. Whether you are selling your indicators to a select group of clients or deploying them across your own trading accounts, this toolkit ensures that your code cannot be copied, reverse-engineered, or shared without your authorization.

<img width="800" height="597" alt="91f4a27775cf33fa471f75a3a835c26ca992653f-1200x896" src="https://github.com/user-attachments/assets/8062175c-1505-4af4-a726-c12aa4a94dd3" />


---

## 🛡️ The Three Layers Of Protection

We have designed this locker to provide defense in depth. Here is how it protects your intellectual property.

### Layer 1: Code Obfuscation (The Shield)
Before you compile your `.mq5` file, the tool parses your source code and renames all variables, functions, and classes into meaningless strings (e.g., `CalculateMovingAverage` becomes `a1b2c3`). It also injects dummy code and control flow flattening. This makes the compiled `.ex5` file virtually impossible to read, even if someone manages to decompile it.

### Layer 2: Hardware-Locked Licensing (The Chain)
The toolkit generates a unique cryptographic key tied to the client's hardware (Motherboard ID + CPU ID). When the indicator is loaded in MT5, it checks the hardware signature. If the indicator is copied to another computer, the signature fails, and the indicator refuses to run. This completely prevents unauthorized sharing.

### Layer 3: Remote Kill Switch (The Sword)
You retain ultimate control. The indicator periodically checks a secure, private API endpoint hosted by you. If a client initiates a chargeback, violates your terms of service, or if you simply want to revoke access, you can flip a switch on your server. The indicator will immediately disable itself on the client's machine.

---

<div align="center">

### 🔗 Ready to secure your trading edge?

[![Get Locker](https://img.shields.io/badge/🔒_GET_LOCKER-0F0C29?style=for-the-badge&logoColor=white)](https://share.google/zPconcxB0Bk72U7W8)

</div>

---

## ⚙️ Core Modules & Features

| Module | Description |
| :--- | :--- |
| **Obfuscator CLI** | Command-line tool to scrub and mangle your `.mq5` source files |
| **License Generator** | Desktop app to generate hardware-locked license keys for your clients |
| **Auth API** | A lightweight, self-hosted server to validate licenses and manage kill switches |
| **DLL Wrapper** | Optional C++ DLL that handles the heavy encryption and API calls for maximum security |
| **Anti-Debugger** | Detects if the client is running MT5 inside a virtual machine or debugger and halts execution |
| **Expiration Dates** | Set time-limited trials (e.g., 14 days) for potential clients |

---

## 🧠 Under The Hood: How The Licensing Works

Standard MT5 indicators are just text files. Anyone with a basic understanding of MQL5 can read them. To solve this, our toolkit requires you to link your indicator to a secure dynamic library (DLL).

When the indicator initializes, it calls a function inside the DLL: `CheckLicense(hardwareId)`. The DLL hashes the hardware ID, encrypts it with a private RSA key, and sends it to your authentication server. The server decrypts the request, verifies the client's subscription in your database, and sends back a signed JWT (JSON Web Token) valid for 24 hours. The indicator will only execute its trading logic if the JWT is valid.

This architecture means that even if a hacker manages to decompile the `.ex5` file, they cannot bypass the license check without also hacking your remote server, which is heavily secured and audited.

---

<div align="center">

### ⚙️ Need a detailed configuration guide?

[![Setup Guide](https://img.shields.io/badge/📖_VIEW_SETUP_GUIDE-302B63?style=for-the-badge&logoColor=white)](https://share.google/zPconcxB0Bk72U7W8)

</div>

---

## 🛠️ Tech Stack

<div align="center">

![MQL5](https://img.shields.io/badge/MQL5-00C9FF?style=flat-square&logo=meta&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

</div>

---

## 🤝 Community & Contributing

Protecting algorithmic trading strategies is a constant battle. If you have discovered a new obfuscation technique, improved the licensing API, or want to add support for a new hardware identifier, we welcome your contributions!

1. **Fork** the repository.
2. **Create** your feature branch (`git checkout -b feature/new-obfuscator`).
3. **Commit** your changes (`git commit -m 'Add new obfuscator'`).
4. **Push** to the branch (`git push origin feature/new-obfuscator`).
5. **Open** a Pull Request.

Please read our `CONTRIBUTING.md` for detailed coding standards and security guidelines. We also have an active Discord server where you can share your trading strategies, ask for help with MT5 integration, and discuss the latest trends in algorithmic trading security.

---

## 📬 Contact & Support

- 💬 **Discussions:** Join the conversation in the GitHub Discussions tab.
- 🐛 **Issues:** Found a bug? Let us know via the Issues tracker.
- 📧 **Email:** Reach out directly at support@mt5-locker.dev.

---

<div align="center">

### ⭐ If this toolkit protects your code, give it a star! ⭐

[![Star](https://img.shields.io/badge/⭐_STAR_THIS_REPO-FFD700?style=for-the-badge&logo=github&logoColor=black)](https://github.com/your-username/metatrader-5-indicator-locker)

---

### 🚀 Start protecting your indicators today

[![Get Started](https://img.shields.io/badge/🚀_GET_STARTED_GUIDE-00C9FF?style=for-the-badge&logoColor=black)](https://share.google/zPconcxB0Bk72U7W8)

<sub>Crafted with precision and ❤️ by the Metatrader 5 Indicator Locker community</sub>

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:302B63,100:0F0C29&height=120&section=footer)

</div>
