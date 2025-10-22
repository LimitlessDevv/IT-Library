# 🐍 Python Virtual Environment

📝 Memo: As a cloud engineer, I often use virtual environments when working on personal projects, like when I wrote test code for the OpenStack Contribution or when I built an AI app using an MCP server.

I’ve always thought of virtual environments as a way to isolate packages, so this time I’m going to organize what they actually are.

## ❓ What is a Python Virtual Environment?

It's a feature that creates an independent, isolated Python workspace for each project. It allows you to install necessary libraries and packages within this isolated space. Because it's an isolated structure, work done in workspace A does not affect workspace B.

## 💥 Why Use It? : To Prevent Dependency Conflicts
The biggest reason to use a virtual environment is to prevent "Dependency Conflicts."

Imagine you install all packages globally on your computer without using a virtual environment:

Project A: Needs pandas v1.0

Project B: Needs pandas v2.0

In this case, you would face the cumbersome situation of having to upgrade or downgrade your pandas version every time you switch projects. Virtual environments solve this problem cleanly.

## ⚙️ Differences in How Python and Java Work

**Python**: By default, all packages installed with pip install are stored in a single "public warehouse" (the site-packages folder). This can cause dependency conflicts.

Therefore, you need to create a virtual environment using `venv`.

**Java**: Unlike Python, Java uses build tools like Maven or Gradle.

Dependencies are declared per project and isolated during the build process, so a separate virtual environment tool like `venv` is not necessary.

## 🚀 How to Use a Python Virtual Environment?
Since Python 3.3, a module named `venv` for creating virtual environments is built-in.

### 1. Create the Virtual Environment 🛠️
Run this command once inside your project folder. This will create a subdirectory (e.g., venv) in your current folder, which contains an independent Python environment.

```
# python -m venv [name_of_virtual_env_folder]
  python -m venv venv
```

### 2. Activate the Virtual Environment ▶️
On Windows (PowerShell/CMD):
```
.\[name_of_virtual_env_foler]\Scripts\activate
```

On Mac / Linux (bash/zsh)
```
source [name_of_virtual_env_foler]\bin\activate
```

### 3. Confirm Activation ✅
Once activated, the name of the virtual environment (e.g., (venv)) will appear at the beginning of your terminal prompt.

From now on, all pip commands you run will apply only inside this virtual environment.

### 4. Install and Use Packages 📦
While the environment is active ((venv) is visible), install packages using pip.

```
pip install pandas requests flask
```

### 5. Share the Project: requirements.txt 🤝
To allow other developers to set up the exact same environment, you should save a list of your installed packages.

```
pip freeze > requirements.txt
```
- `pip freeze`: Shows a list of all packages installed in the currently active venv.
- `> requirements.txt` : Saves that list to a file named requirements.txt.

If you commit this requirements.txt file to Git, other team members can install all the exact same packages at once using pip install -r requirements.txt.

### 6. Git Configuration (.gitignore) 🚫
The virtual environment folder itself (e.g., venv/) contains all the installed library files and can be very large. You must add it to your .gitignore file to prevent it from being uploaded to Git.

Example `.gitignore` entry:
```
/venv
```

### 7. Deactivate the Virtual Environment ⏹️
When you're done working, you can exit the environment using the deactivate command.
```
deactivate
```