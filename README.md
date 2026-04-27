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
<summary>Вывод</summary>
  
```bash
hint: Using 'master' as the name for the initial branch. This default branch name
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
Инициализирован пустой репозиторий Git в /Users/aleksandrgolikov/workspace/projects/laba2/.git/
```
</details>

Команда: `$ git add .`
добавляю все измененные и новые файлы в текущей директории (и поддиректориях) в индекс Git 

Команда: `$ git status`
смотрю текущее состояния рабочего каталога и индекса 

<details>
<summary>Вывод</summary>

```bash
Текущая ветка: master

Еще нет коммитов

Изменения, которые будут включены в коммит:
  (используйте «git rm --cached <файл>...», чтобы убрать из индекса)
	новый файл:    laba2/laba2.xcodeproj/project.pbxproj
	новый файл:    laba2/laba2.xcodeproj/project.xcworkspace/contents.xcworkspacedata
	новый файл:    laba2/laba2.xcodeproj/project.xcworkspace/xcuserdata/aleksandrgolikov.xcuserdatad/UserInterfaceState.xcuserstate
	новый файл:    laba2/laba2.xcodeproj/xcuserdata/aleksandrgolikov.xcuserdatad/xcschemes/xcschememanagement.plist
	новый файл:    laba2/laba2/main.cpp
```
</details>

Команда: `$ git commit -m "Instal commit: Xcode project and hello world"`
фиксация проиндексированных изменений (тех, что добавил через git add .) и создание новой записи в истории репозитория

<details>
<summary>Вывод</summary>

```bash
[master (корневой коммит) 8257623] Instal commit: Xcode project and hello world
 5 files changed, 312 insertions(+)
 create mode 100644 laba2/laba2.xcodeproj/project.pbxproj
 create mode 100644 laba2/laba2.xcodeproj/project.xcworkspace/contents.xcworkspacedata
 create mode 100644 laba2/laba2.xcodeproj/project.xcworkspace/xcuserdata/aleksandrgolikov.xcuserdatad/UserInterfaceState.xcuserstate
 create mode 100644 laba2/laba2.xcodeproj/xcuserdata/aleksandrgolikov.xcuserdatad/xcschemes/xcschememanagement.plist
 create mode 100644 laba2/laba2/main.cpp
```
</details>

Команда: `$ git remote add origin git@github.com:2dmpjv8fgy-commits/laba2.git`
установка связи между локальным рабочим окружением и удаленным сервером GitHub

Команда: `$ git branch -M main`
переименование основной ветки локального репозитория в `main`

Команда: `$ git push -u origin main`
отправка локальных коммитов в удаленный репозиторий на GitHub

<details>
<summary>Вывод</summary>

```bash
Перечисление объектов: 16, готово.
Подсчет объектов: 100% (16/16), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (13/13), готово.
Запись объектов: 100% (16/16), 13.04 KiB | 13.04 MiB/s, готово.
Total 16 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To github.com:2dmpjv8fgy-commits/laba2.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```
</details>


### Part 2: Работа с ветками
Создана ветка `patch1`, изменен код (добавлены комментарии и ввод имени), выполнен merge.

Команда: `$ git checkout -b patch1` cоздание новой ветки patch1 и переключение на неё

Команда: `$ git add laba2/laba2/main.cpp` добавление конкретного файла в область подготовленных файлов. Использование точного пути к `main.cpp` позволяет изолированно зафиксировать изменения в исходном коде, не затрагивая конфигурационные файлы среды разработки Xcode.

Команда: `$ git commit -m "added comments and fixed code style"`
создание коммита в ветке patch1. Эта операция сохраняет изменения, сделанные в файле `main.cpp`

<details>
<summary>Вывод</summary>

```bash
[patch1 1246db3] added comments and fixed code style
 1 file changed, 6 insertions(+), 2 deletions(-)
```
</details>

Команда: `$ git push origin patch1`
oтправка локальной ветки patch1 в удаленный репозиторий на GitHub

<details>
<summary>Вывод</summary>

```bash
Перечисление объектов: 9, готово.
Подсчет объектов: 100% (9/9), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (5/5), 517 bytes | 517.00 KiB/s, готово.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/2dmpjv8fgy-commits/laba2/pull/new/patch1
remote: 
To github.com:2dmpjv8fgy-commits/laba2.git
 * [new branch]      patch1 -> patch1
```
</details>

Команда: `$ git checkout main`
переключение рабочего каталога на ветку `main`

<details>
<summary>Вывод</summary>

```bash
M	laba2/laba2.xcodeproj/project.xcworkspace/xcuserdata/aleksandrgolikov.xcuserdatad/UserInterfaceState.xcuserstate
Переключились на ветку «main»
Эта ветка соответствует «origin/main».
```
</details>

Команда: `$ git merge patch1`
cлияние ветки patch1 с текущей активной веткой `main` это позволяет объединить результаты изолированной разработки с основной кодовой базой проекта, сохраняя при этом целостность истории коммитов

<details>
<summary>Вывод</summary>

```bash
Обновление 8257623..1246db3
Fast-forward
 laba2/laba2/main.cpp | 8 ++++++--
 1 file changed, 6 insertions(+), 2 deletions(-)
```
</details>

Команда: `$ git push origin main` синхронизация локальной ветки `main` с удаленным репозиторием. Эта операция переносит результат слияния веток на сервер в GitHub, завершая рабочий цикл по внесению правок в проект

<details>
<summary>Вывод</summary>

```bash
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To github.com:2dmpjv8fgy-commits/laba2.git
   8257623..1246db3  main -> main
```
</details>





