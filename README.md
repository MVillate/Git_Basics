# GIT BASICS

## Commands

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

### Commiting

```bash
git commit -m *message*
```

### Adding the repository to Github

Previously a Github blank repository has to be created

```bash
git remote add origin git@github.com:MVillate/Git_Basics.git
```

<<<<<<< HEAD
Verify the link with the next command
=======
Verify the link with the following command 
>>>>>>> 6aa604d4e70e2e718da97b0ae60bda9283af094c

```bash
git remote -v
```

push the local repository to Github the first time use the -u flag. The -u flag is used to set origin as the upstream remote in your git config. As you push a branch successfully or up to date it, it adds upstream reference. As you push local branch with git push -u option, that local branch is linked with the remote branch automatically

```bash
git push -u origin master
```

Then, to keep on pushing the changes no flags are required

```bash
git pull origin master
git push origin master
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
