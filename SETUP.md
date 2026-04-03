# ⚙️ Aura Farming – Setup Guide

This guide explains how to set up the project using a modern Python workflow with `uv` and configure access to datasets via Kaggle.

---

## 🧰 Prerequisites

Ensure the following are installed:

* Python 3.9 or higher
* Git
* VS Code (recommended)

---

## Install uv

### Mac / Linux:

```bash
curl -Ls https://astral.sh/uv/install.sh | sh
```

### Windows (PowerShell):

```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Verify:

```bash
uv --version
```

---

## Clone the Repository

```bash
git clone https://github.com/mayankpriy/AuraFarm.git
cd AuraFarm
```

---

## Environment Setup

```bash
uv venv
source .venv/bin/activate
uv pip install pandas numpy mysql-connector-python python-dotenv jupyter kaggle
```

### Windows:

```bash
uv venv
.venv\Scripts\activate
uv pip install pandas numpy mysql-connector-python python-dotenv jupyter kaggle
```

---

## Kaggle Setup

### Step 1: Create API Token

1. Go to https://www.kaggle.com/settings
2. Scroll to **API Tokens**
3. Create a new token
4. Copy your:

   * Username
   * Key

---

### Step 2: Configure Credentials

```bash
mkdir -p ~/.kaggle
nano ~/.kaggle/kaggle.json
```

Add:

```json
{
  "username": "your_username",
  "key": "your_key"
}
```

---

### Step 3: Secure File

```bash
chmod 600 ~/.kaggle/kaggle.json
```

---

### Step 4: Verify

```bash
kaggle datasets list
```

---

## Download Dataset (Example)

```bash
kaggle datasets download -d asifxzaman/e-commerce-behavior-dataset8000-users
unzip e-commerce-behavior-dataset8000-users.zip
```

Move dataset:

```bash
mv *.csv data/csv/raw/events_kaggle.csv
```

---

## Working with Notebooks

### VS Code

* Open `.ipynb` file
* Select `.venv` as kernel
* Run cells

---

## Running Commands

Use:

### VS Code Terminal (recommended)

```
Ctrl + `
```

---

## Project Structure

```text
AuraFarm/
├── notebooks/
├── data/
├── scripts/
├── config/
├── pyproject.toml
```

---

## Guidelines

* Use relative paths:

  ```
  ../data/csv/raw/events.csv
  ```
* Keep datasets small
* Ensure notebooks run without errors
* Do not commit credentials

---

## Objective

Provide a consistent and reproducible development environment for debugging real-world data scenarios.

---
