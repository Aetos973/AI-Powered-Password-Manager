# 🔐 AI-Powered Password Manager (Offline-First)

Secure. Smart. Private.  
A developer-grade password manager with AI-assisted password generation, strength analysis, and secure encrypted storage — built with Python, PostgreSQL, and offline-compatible tools.

---

## ✨ Features

- ✅ **Secure user registration and authentication**
- 🔐 **Encrypted password storage using `bcrypt` + `cryptography`**
- 📊 **ML-based password strength classification**
- 🧠 **Offline AI suggestions for strong, unique passwords**
- 🧪 CLI + Optional FastAPI interface
- 📦 Local-only / air-gapped usage supported
- 📁 Backup/export functionality

---

## ⚙️ Technologies Used

| Category         | Tech Stack                        |
|------------------|-----------------------------------|
| Language         | Python 3.11+                      |
| Database         | PostgreSQL (local or hosted)      |
| Encryption       | bcrypt, cryptography              |
| ORM              | SQLAlchemy                        |
| ML/AI            | scikit-learn, zxcvbn, llama-cpp   |
| Offline LLM      | llama-cpp-python / ctransformers  |
| CLI              | typer, rich                       |
| Optional UI      | FastAPI + Uvicorn                 |

---

## 📁 Folder Structure

```

AI-Powered-Password-Manager/
├── cli/                   # CLI tools and command-line interface
├── web/                   # Optional FastAPI interface (if needed)
├── db/                    # SQL scripts, seed data, and migrations
├── ml/                    # ML model training + evaluation scripts
│   ├── model.pkl          # Trained password strength classifier
│   └── train_model.py
├── models/                # Offline LLMs (.gguf or quantized models)
├── llm_tools/             # LLM-powered password generators, formatters
├── prompts/               # Prompt templates + logs for password AI
│   ├── generation.md
│   ├── critique-tests.md
│   └── README.md
├── data/                  # Encrypted vault data, logs, or exports
├── config.env             # Local env vars
├── requirements.txt
├── changelog.md
└── README.md

````

---

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/Aetos973/AI-Powered-Password-Manager.git
cd AI-Powered-Password-Manager
````

### 2. Create virtual environment & install requirements

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 3. Configure your environment

Create a `.env` file or edit `config.env`:

```env
DATABASE_URL=postgresql://user:pass@localhost:5432/password_vault
LLM_MODEL_PATH=models/llama-password.gguf
```

### 4. Run the CLI app

```bash
python cli/main.py
```

---

## 🧠 Example Offline LLM Prompt

Prompt: "Generate 5 unique, secure passwords for a developer account. Avoid common words and ensure at least one symbol."

Response (TinyLLaMA): 
- &Gr8t^Feather_Bot9
- M!nor@Pulse78

---

## 📈 Roadmap

* [ ] Web UI with FastAPI
* [ ] Role-based vaults (multi-user support)
* [ ] Auto-password rotation
* [ ] Integration with YubiKey / hardware auth
* [ ] Full audit trail / changelog viewer

---

## 🔒 Disclaimer

This project is **educational and experimental**. Please do your own security audit before using it in production. Use responsibly.

---

## 🤝 Contributing

Open issues, share improvements, or fork and extend!
Pull requests are welcome.

---

## 📜 License

MIT — do what you want, but stay secure.

---
