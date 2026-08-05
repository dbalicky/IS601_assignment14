# Setup

## Directory Setup

### Clone module 14 from github
```bash
git clone git@github.com:kaw393939/module14_is601.git
```

### Create directory for assignment 14
```bash
# Go to is601_projects directory
# cd is601_projects/
mkdir assignment14/

#Go to assignment14 dir
cd assignment14/
```
### Copy files and directories from cloned repo to assignment14/ dir
```bash
# In assignment14 dir
# For each necessary file and directory
cp -r ~/module14_is601/<file/dir> .
```

### Open in vscode
```bash
code .
```


## Initialization

### Change python version to 3.10
```bash
pyenv local 3.10

# Checking version
python3 --version
```

### Create and activate virtual environment
```bash
python3 -m venv venv

source venv/bin/activate
```

### Initialize git repo
```bash
git init
```

### Set remote github repo
```bash
git remote add origin git@github.com:dbalicky/IS601_assignment14.git
```

### Initial commit and push
```bash
git add .

git commit -m 'initial commit'

git push --set-upstream origin main

# For subsequent pushes
git push
```

