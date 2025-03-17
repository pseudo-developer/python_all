# Python All Project Setup Guide

This document provides a step-by-step guide for setting up the project environment and initializing Git. It's meant to be a quick reference for setting up a similar project in the future.

---

## 1. Virtual Environment Setup

### **Create a Virtual Environment in the Project Folder**

To begin, create a virtual environment for the project to keep your dependencies isolated:

```bash
python -m venv python_env
```

### **Activate the Virtual Environment**
After creating the virtual environment, activate it using the following command:

For Windows:
```python_env\Scripts\activate
```

Once activated, you should see (python_env) in the command prompt, indicating that the virtual environment is active.

## 2. Create ".gitignore" File
Navigate to the project folder and create a file called .gitignore.
Write the virtual environment name with a slash to include it as a directory in this file.
Once a directory (or a file) is included in this file, even if we set up Git for the project folder, the included directory (or file) in the .gitignore file won't be tracked by Git for changes.
Hence, we can exclude the files and packages downloaded in the virtual environment folder/directory.

1. Navigate to the project folder.
2. Manually create a file called `.gitignore` in this directory.
3. Open the file, and write "python_env/" in it.
4. Save the file and close it.
5. The virtual environment files and packages won't be tracked by Git for any changes we do in those files.


## 3. Initialize Git Repository (Local) + Remote
Initialize Git Repository (Local)
Now, initialize the Git repository in the project folder:
```git init ```

- Add Project Information to Readme.md as First Commit
Create a Readme.md file and add some initial information:
``` echo "python_all project" >> Readme.md ```

- Rename the Branch to main
Next, we need to rename the branch to main. GitHub’s default branch is now called "main," so we follow the best practice by renaming our local branch to main as well:
``` git branch -M main ```

- Add Remote Repository
Link your local repository to the remote GitHub repository using this command:

``` git remote add origin https://github.com/pseudo-developer/python_all.git ```

- Stage the Files for Commit

Add the files to Git staging:

``` git add . ```

- Check the Status
``` git status ```

You should see something like this:
```On branch main
No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
        new file:   Readme.md
```

- Commit the Changes
```git commit -m "first commit after git initialization"```

This will create your first commit with the changes. The output will look like this:

```
[main (root-commit) 5c84928] first commit after git initialization
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore
 create mode 100644 Readme.md
```


**NOTE -** If your commit doesn't succussfully execute, and you see a message on screen that user.name and user.email needs to be set in git, then firstly we need to set them up using terminal.

Now there are two scopes over which user.name and user.email can be set-up:
1. Global level (for your pc/local)
2. Repo level.

If on personal use, we can go for Global scope level set-up.

- Global level set-up:
```
Set for global level:
git config --global user.name "Mona Lisa"

git config --global user.email "YOUR_EMAIL"
```

- Repo level set-up:
```
Set for repo level :
- git config user.name "Mona Lisa" -> sets your name for current repo. To verify -> git config user.name
- git config user.email "YOUR_EMAIL" -> sets your name for current repo. To verify -> git config user.email
```

***Now you’ve successfully initialized the project with Git and made your first commit.***


## 4. Install Jupyter and IPython Kernel
Now that the Git setup is complete, let’s move on to setting up Jupyter and IPython kernel for the project.

- Install Jupyter
With the virtual environment activated, install Jupyter:
```pip install jupyter```

- Install IPython Kernel
Install the IPython kernel to allow Jupyter to use the virtual environment:
```pip install ipykernel```

- Register the Virtual Environment as a Jupyter Kernel
After installing ipykernel, register the virtual environment as a new kernel for Jupyter:
```python -m ipykernel install --user --name=python_env --display-name "Python (python_env)"```

--name=python_env: The name for the kernel.
--display-name "Python (python_env)": The name that will show up in Jupyter’s kernel list.


## 5. Open VS Code and Configure the Kernel
- Open VS Code and open the folder where you’ve created the virtual environment.
- Open a Jupyter notebook file (.ipynb) or create a new one.
- In the top-right corner of the notebook, you’ll see a Kernel selector.
- Click on the kernel name and select "Python (python_env)" from the dropdown. This will switch the kernel to the one associated with your virtual environment.

## 6. Create requirements.txt for Your Project
Once you’ve installed the necessary packages (e.g., Jupyter, ipykernel, etc.), you can create a requirements.txt file to capture all the installed libraries in your virtual environment.

- Generate requirements.txt
With the virtual environment activated, run the following command to generate the requirements.txt file:
```pip freeze > requirements.txt```

This will create a requirements.txt file in your project directory, listing all the installed packages and their versions. For example:

```ipykernel==6.6.0
jupyter==1.0.0
numpy==1.21.2
pandas==1.3.3
```

## 7. Install Dependencies from requirements.txt (for future use)
In the future, if you or anyone else needs to replicate the environment, simply run the following steps:

- Create and activate a new virtual environment.
- Install the dependencies from the requirements.txt file:
```pip install -r requirements.txt```

This will install all the required libraries in the new environment, making it identical to the original one.

### **Summary**
With this setup, you now have:

- A Python virtual environment isolated from your global Python installation.
- Jupyter notebooks running with the virtual environment kernel in VS Code.
- A requirements.txt file that helps you easily replicate the environment in the future.

-----

### **Additional Notes**
- Virtual Environment Activation: Remember to activate your virtual environment every time you work on this project. Run python_env\Scripts\activate (Windows) or source python_env/bin/activate (macOS/Linux) before working.

- Managing Dependencies: Whenever you install new packages, don’t forget to update the requirements.txt by running pip freeze > requirements.txt again.










