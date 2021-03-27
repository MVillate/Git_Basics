# GIT BASICS

## Local commands and link to GitHub

### Initialization

```bash
git init
```

### Verification

```bash
git status
```

```bash
git log
```

```bash
git branch -a
git remote -v
```

### Staging

```bash
git add .
git add -A
git add *filename*
git reset
git reset *filename*
```

### Diff

```bash
git diff
git diff -r HEAD
```

### Commiting

```bash
git commit -m *message*
```

### Adding the repository to Github

Note: Now the origin master is not used. Use main

```bash
git branch -M main
```

Previously a Github blank repository has to be created

```bash
git remote add origin git@github.com:MVillate/Git_Basics.git
```

Verify the link with the next command

```bash
git remote -v
```

push the local repository to Github the first time use the -u flag. The -u flag is used to set origin as the upstream remote in your git config. As you push a branch successfully or up to date it, it adds upstream reference. As you push local branch with git push -u option, that local branch is linked with the remote branch automatically

```bash
git push -u origin main
```

Then, to keep on pushing the changes no flags are required

```bash
git pull origin main
git push origin main
```

To remove the remote origin

```bash
git remote remove origin
```

### Public Key generation

The following command will generate a key in ~/.ssh. By default the name is id_rsa and id_rsa.pub

```bash
ssh-keygen -t rsa -b 4096 -C "manuel.villate@gmail.com"
manuel_villate@PRG-116637-C02CK1BXMD6W .ssh % ls
id_rsa		id_rsa.pub	known_hosts
```

Copy the public key to github

```bash
pbcopy < ~/.ssh/id_rsa.pub
```

Add the key to https://github.com/settings/ssh/new

### Multiple keys

folder ~/.ssh config file

```bash
Host *
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_rsa_gh
```

Modify the line IdentityFile to add ~/.ssh/id_rsa_gh_mck then 

```bash
ssh-add  ~/.ssh/id_rsa_gh
```

## Branches

```bash
git branch -M main
```

### Creating and selecting branches

To create a branch

```bash
git branch name_prompt
```

To select the branch to start working on it. After this point you can start commiting in this branch normally.

```bash
git checkout name_prompt
```

To verify the existing branches

```bash
(venv) PRG-116637-C02CK1BXMD6W:Git_Basics manuel_villate$ git branch
* main
  name_prompt
```

To associate for the first time the local branch to a remote repository
```
git push -u origin name_prompt
```

To verify the existing branches including the remote

```bash
git branch -a
  main
* name_prompt
  remotes/origin/main
  remotes/origin/name_prompt
```

### Merging Branches

To merge the branch with main, select the main branch

```bash
git checkout main
```

Pull the latest changes from the main branch if there are some

```bash
git pull origin main
```

Merge the branches locally

```bash
git merge name_prompt
```

Confirm that the branches have merged

```bash
git branch --merged
```

Push the new merged branch to the remote repository. After that, GitHub will show the following message in the name_prompt branch **"This branch is even with main."**

```bash
git push origin main
```

### Deleting Branches

Once the branches have merged, the non-main branch is no longer necessary. To delete it locally, use the following command

```bash
git branch -d name_prompt
```

To delete the branch in the remote repository

```bash
git push origin --delete name_prompt
```

To verify that the unnecessary branch has been deleted locally and in the remote repository

```bash
git branch -a
* main
  remotes/origin/main
```
