## Version control

Install and configure git
```bash
$ sudo apt install git

#Configuring git
$ git config --global user.name "login name computer"
$ git config --global user.email "email"

# setting default name for main branch in a project
$ git config --global init.defaultBranch main
```

Ignoring files
```python
# To avoid git keeping track of unneccary files.
# Make a file called .gitignore
# add directorys such as __pycache__/
__pychache__/
```

Initialize repository
```bash
# navigate to the project directory
project_name$ git init

#checking status
project_name$ git status

# adding all the projectfiles to the repo
project_name$ git add .

# Making a commit / snapshot
project_name$ git commit -m "snapshot name"

# checking the log
project_name$ git log
# or
project_name$ git log --pretty=oneline #simple version

# second commit -a flag tells git to add modified files 
project_name$ git commit -am "New snapshot"

# go back to last commit / snapshot
project_name$ git restore . # all files
project_name$ git restore *filename*
```

Checking out previous commits
```bash
# revisit any commit in the log
$ git log --pretty=oneline
0eb4735c72478c885cf9373bb288a7580ae1ccb9 (HEAD -> main) Ver 1.0
8c95b3b493e675b9ffd07ec30145adb9e74d5acd Started on project

#checkout to previous commit
$ git checkout 8c95b3 # first six characters of ID

# to undo and get back to latest commit
$ git switch -

# reset project to a previous commit from main branch
$ git reset --hard 8c95b3 # commit we want to go back to
```

Deleting the repository:
```bash
# either delete the .git directory in a filebrowser (hidden)

# from cli
$ rm -rf .git/
```

collaboration:
```bash
git push -u origin main

git pull origin main   
```

---
