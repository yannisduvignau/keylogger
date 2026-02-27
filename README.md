# ⌨️ Keylogger — Educational Project

> ⚠️ **Warning**: This project is strictly for educational purposes to understand how keystroke logging works. Never use it on systems or devices without explicit authorization from the owner. Unauthorized use is illegal and unethical.

---

## 📖 About

This project is a minimal keylogger built in Python. It listens for keyboard events in the background and logs every keystroke — including special keys — to a timestamped log file.

It is designed to help understand how keyloggers work at a low level: how input events are intercepted at the OS level, how regular and special keys are handled differently, and how data is silently written to a file. These concepts are fundamental in cybersecurity, particularly in the study of spyware, malware analysis, and endpoint defense.

The project uses **pynput**, a cross-platform Python library for monitoring and controlling input devices. The codebase is intentionally kept simple and readable to keep the focus on the underlying concepts.

---

## 📋 Prerequisites

- Python 3.x
- pip

---

## 🚀 Installation & Usage

### 1. Create a Python virtual environment

```bash
python3 -m venv env
```

### 2. Activate the virtual environment

```bash
# Linux / macOS
source env/bin/activate

# Windows
env\Scripts\activate
```

### 3. Install dependencies

```bash
echo "pynput" > requirements.txt
pip install -r requirements.txt
```

### 4. Create the `.gitignore` file

```bash
echo -e ".gitignore\nenv/\nrequirements.txt\n.env*\n*.log" > .gitignore
```

### 5. Run the keylogger

```bash
python3 main.py
```

Keystrokes will be logged to a file named `keylog_YYYY-MM-DD_HH-MM-SS.txt` in the current directory.

### 6. Deactivate the virtual environment

```bash
deactivate
```

---

## 📁 Project Structure

```
.
├── main.py          # Keylogger script
├── requirements.txt # Python dependencies
├── keylog_*.txt     # Generated log files (auto-created at runtime)
└── README.md        # Documentation
```

---

## 🔑 How it works

When `main.py` is run, it registers a listener on the keyboard using `pynput`. Every time a key is pressed:

- **Regular keys** (letters, numbers, symbols) are logged as plain characters.
- **Special keys** (Enter, Shift, Ctrl, etc.) are logged by their name.

All events are written with a timestamp to a `.txt` log file, which is created automatically when the script starts.

---

## ⚖️ Legal Disclaimer

This code is provided **for educational purposes only**. Any use on systems or devices without explicit authorization is illegal and may result in criminal prosecution.