## Git 

This is a little cheatsheet about [Git](https://git-scm.com).

### Help
```
git help
git clone --help
git log --help
git add --help
git commit --help
git push --help
git pull --help
```

### Init a repository
```
git init
```

### Clone full repository
```
git clone https://github.com/andersonlfeitosa/cheatsheets.git
```

### Clone last 16 commits
```
git clone --depth=16 https://github.com/andersonlfeitosa/cheatsheets.git 
```

### Log
```
git log --pretty
git log --stat
git log --graph
```

### Status
```
git status 
```

### Rename or move file
```
git mv old_file new_file

mv old_file new_file
git rm old_file
git add new_file
```

### Rollback the last commit
```
git commit --amend
git reset HEAD^
```

### Add remote origin to repository
```
git remote add origin https://github.com/andersonlfeitosa/cheatsheets.git
```

### Add file to repository
```
git add readme.md
```

### Commit
```
git commit -m "commit message"
```

### Push 
```
Setting upstream:
git push -u origin master
```

### Tag
```
Create tag:
git tag app-1.0.0

Send a specific tag to origin:
git push origin app-1.0.0

Send all tags to origin:
git push origin --tags
```

### Branch
```
Create branch and switch:
git checkout -b app-1.0.1

or

git branch app-1.0.1
git checkout app-1.0.1

Send branch to upstream:
git push origin app-1.0.1


Delete branch:
git checkout -d app-1.0.1
```

### Merge (on specific branch)
```
git merge hotfix
```

### Change remote URL 
```
git remote set-url origin new_url
```

