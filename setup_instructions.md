# ⚙️ Setup Instructions for Auto Git Push Script

This guide helps you automate Git commits and pushes from VS Code using Python and Windows Task Scheduler – no Git GUI or GitLab needed.

---

## 🧰 Requirements

- Python 3.x installed
- Git installed
- VS Code installed
- A GitHub repository cloned to your local system
- Internet connection

---

## 🚀 Project Structure

```

AutoPushGit/
│
├── auto\_push\_script.py        # Script to auto commit & push
├── commands\_used.txt          # Terminal commands used
├── setup\_instructions.md      # This file
├── logs/
│   └── auto\_push\_log.txt      # Logs of each push
└── screenshots/
└── ...                    # Add your screenshots here

````

---

## 🔧 Step-by-Step Setup

### ✅ Step 1: Clone the Repository

```bash
git clone https://github.com/Haricharhan/MySolvedProblems.git
````

> Or clone your own GitHub repo using:

```bash
git clone https://github.com/your-username/your-repo-name.git
```

---

### ✅ Step 2: Create `auto_push_script.py`

Inside your repo folder, create a Python file with the following logic:

```python
# auto_push_script.py
import os
import datetime

def log(msg):
    with open("logs/auto_push_log.txt", "a") as f:
        f.write(f"{datetime.datetime.now()} - {msg}\n")

log("Running auto push")

os.system("git add .")
os.system("git commit -m \"Auto Push from Script\"")
os.system("git push origin main")
```

> 💡 Make sure the branch name is `main`. If yours is `master`, change `origin main` to `origin master`.

---

### ✅ Step 3: Test It Manually

Run the script in VS Code terminal:

```bash
python auto_push_script.py
```

If it works, you’ll see your commits pushed to GitHub. Logs will be added in `logs/auto_push_log.txt`.

---

## 🕒 Automate with Windows Task Scheduler

This will run the script automatically at your chosen interval (e.g., every 2 hours).

---

### 🧭 Step 4: Open Task Scheduler

* Press `Windows + R`, type `taskschd.msc`, and hit Enter.

---

### 🧱 Step 5: Create New Task

1. Click **Create Basic Task**
2. Name: `Auto Git Push`
3. Trigger: Daily (or as per your need)
4. Start time: Set the time
5. Action: **Start a program**

---

### 🖥️ Step 6: Choose Python Script

* Program/script: `python`
* Add arguments (replace path accordingly):

  ```bash
  auto_push_script.py
  ```
* Start in (directory path of your script, without trailing slash)

✅ Example:

* Program/script: `python`
* Add arguments: `auto_push_script.py`
* Start in: `C:\Users\YourName\Projects\AutoPushGit`

---

### ⏰ Step 7: Finish & Run

* Click **Finish**
* Right-click your task > **Run** to test

---

## 📁 Output Files

* **logs/auto\_push\_log.txt** → Tracks every commit & push with timestamps
* **screenshots/** → Add screenshots of task scheduler & GitHub push
* **commands\_used.txt** → All Git commands used during setup

---

## ✅ Sample Commands (Included in `commands_used.txt`)

```bash
git init
git remote add origin https://github.com/your-username/your-repo.git
git pull origin main
git add .
git commit -m "First Commit"
git push origin main
```

---

## 🧠 Why This Project Is Unique

Unlike tutorials copied from YouTube, this automation was completely self-designed. The idea came from real need and logic, not from copy-paste solutions. It's a great example of **automation thinking + real-time scheduling + Git workflow**.

---


---

Made with ❤️ by [Haricharhan](https://github.com/Haricharhan)

```
