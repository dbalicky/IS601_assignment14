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

## Installing dependencies

### Install dependencies from requirements.txt
```bash
pip install -r requirements.txt
```


# Docker setup

## Create and link Docker repo

**Create docker repository**

dbal7/is601_assignment14

**Change .github/workflows/test.yml tags to reflect**
```bash
tags: |
   dbal7/is601_assignment14:latest
   dbal7/is601_assignment14:${{ github.sha }}
```
```bash
cache-from: type=registry,ref=dbal7/is601_assignment14:cache
```

### Generate and link personal access tokens for docker - github actions

1. Navigate to Account Settings -> Personal Account Tokens
2. Click Generate new token
3. Name - 'module14', Access permissions - Read and Write
4. Click Generate
5. In assignment14 Github repo, Navigate to Settings -> Secrets and Variables -> Actions
6. Click New repository secret
7. Name - DOCKER_USERNAME, Secret - dbal7
8. Click Add secret
10. Add new secret 
11. Name - DOCKERHUB_TOKEN, Secret - 'personal access token generate from docker'
12. Click Add secret

## Build docker image and tag to dockerhub repo

**Make sure docker desktop is open, shutdown and reopen if issues with docker commands**

### Check any currently running images
```bash
docker compose ps
```


# Issues and Fixes

## Dependency version issue

### Update dependency versions in requirements.txt
```bash
cffi==1.17.1 --> 2.0.0
cryptography==44.0.0 --> 50.0.0
fastapi==0.115.8 --> 0.139.0
h11==0.14.0 --> 0.16.0
httpcore==1.0.7 --> 1.0.9
pyasn1==0.6.1 --> 0.6.4
python-jose==3.3.0 --> 3.5.0
python-multipart==0.0.20 --> 0.0.30
# remove starlette
typing-extensions==4.12.2 --> 4.13.2
urllib3==2.3.0 --> 2.7.0
```

### Fix other dependency issues in Dockerfile
**Remove part of code in line 16**
```bash
\ setuptools>=70.0.0 wheel
```

### Add to requirements.txt
```bash
jaraco.context==6.1.0
msgpack==1.2.1
setuptools==78.1.1
wheel==0.46.2
```

**Run to update versions**
```bash
pip install --upgrade -r requirements.txt
```