# Laboratory work II

Данная лабораторная работа посвещена изучению систем контроля версий на примере Git.

## Tasks
1. Создать публичный репозиторий `laba2`.
2. Настроить локальный репозиторий и связать его с GitHub через SSH.
3. Выполнить коммиты в ветку `main`.
4. Работа с ветками: создать `patch1`, внести изменения и выполнить слияние (merge).
5. Составить отчет.

## Execution

### Part 1: Первый коммит
Создан проект в Xcode, инициализирован Git.

Команда: `$ git init`
<details>
<summary>hint: Using 'master' as the name for the initial branch. This default branch name
hint: will change to "main" in Git 3.0. To configure the initial branch name
hint: to use in all of your new repositories, which will suppress this warning,
hint: call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
hint:
hint: Disable this message with "git config set advice.defaultBranchName false"
Инициализирован пустой репозиторий Git в /Users/aleksandrgolikov/workspace/projects/laba2/.git/</summary>

```bash
$ git init
$ git remote add origin git@github.com:2dmpjv8fgy-commits/laba2.git
$ git add .
$ git commit -m "Instal commit: Xcode project and hello world"
$ git push -u origin main
```

### Part 2: Работа с ветками
Создана ветка `patch1`, изменен код (добавлены комментарии и ввод имени), выполнен merge.

```bash
$ git checkout -b patch1$ git add laba2/laba2/main.cpp
$ git commit -m "added comments and fixed code style"
$ git push origin patch1
$ git checkout main
$ git merge patch1
$ git push origin main
```


