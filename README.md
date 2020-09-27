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

Verify the link with the command 

```bash
git remote -v
```

push the local repository to Github

```bash


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
