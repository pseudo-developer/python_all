# python_all Project

This document provides a step-by-step guide for setting up the project environment and initializing Git. It’s meant to be a quick reference for setting up a similar project in the future.

## 1. Virtual env set-up 
- **Create a Virtual Environment in the Project Folder**

To begin, create a virtual environment for the project to keep your dependencies isolated:

```bash
python -m venv python_env
```

- **Activate the Virtual Environment**
After creating the virtual environment, activate it using the following command:

For Windows:
```
python_env/Scripts/activate
```
Once activated, you should see (python_env) in the command prompt, indicating that the virtual environment is active.


## 2. Create ".gitignore" file:

- Navigate to the project folder and create a file called ".gitignore".
- Write the virtual environment name with a slash to include it as a directory in this file.
- Once a directory (or a file) is included in this file, even we set-up git for the project folder, the included directory (or file) in ".gitignore" file won't be tracked by git for changes. 
- Hence, we can exclude the files and packages downloaded in the virtual environment folder/directory set-up by us.

```
1. Navigate to project folder.
2. Manually create a file called .gitignore in this directory.
3. Open the file, and write "python_env/" in it
4. Save the file and close it.
5. The virtual env files and packages won't be tracked by Git further for any changes we do in those files.
```


## 3. Initialize Git Repository (local) + Remote


**Initialize Git Repository (local)** :
Now, initialize the Git repository in the project folder:

```
git init
```

For example, Add Project Information to Readme.md as your first commit. Lets create the Readme.md file first:

```
echo "python_all project" >> Readme.md
```

**Rename the Branch to main :**
Next we need to Rename the Branch to main. Because these days, github's master branch is called "main". So if we keep our local master branch also as "main", it would be nice practice and will help us pushing changes from local "main" to remote "main". 

Let's rename our master branch in local to "main" using below command:

```
git branch -M main
```

**Add Remote Repository :** 

Link your local repository to the remote GitHub repository using this command:

```
git remote add origin https://github.com/pseudo-developer/python_all.git
```

**Stage the Files for Commit -**
Next, add the files to Git staging:

```
git add .
```

**Check the Status -**
To see which files are staged and ready to be committed, run:

```
git status
```

You should see something like this:

```
On branch main
No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
        new file:   Readme.md
```

**Commit the Changes :**

```
git commit -m "first commit after git initialization"
```

This will create your first commit with the changes. The output will look like this:

```
[main (root-commit) 5c84928] first commit after git initialization
 1 files changed, 1 insertion(+)
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
