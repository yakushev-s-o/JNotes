##### [<-- back to README](/README.md)

## Git

### Общие команды

`git init <project-name>` // создать новый локальный репозиторий с заданным именем.  
`git clone <url>` // загрузить проект и его полную историю изменений.  
`git add .` // сделать все измененные файлы готовыми для коммита.  
`git add <fileName>` // сделать указанный файл готовым для коммита.  
`git add '*.txt'` // добавить только файлы, соответствующие указанному выражению.  
`git add --patch fileName` // позволяет выбрать какие изменения из файла добавятся в коммит.  
`git mv [oldFile] [renamedFile]` // изменить имя файла и добавить в индекс коммита.  
`git commit` // записать изменения в репозиторий. для написания сообщения откроется назначенный редактор.  
`git commit -m "commit"` // записать изменения с заданным сообщением.  
`git commit -am "commit”` // создает коммит всех проиндексированных изменений с заданным сообщением.  
`git commit --amend / -m` // добавить изменения к последнему коммиту / без вызова редактора.  
`git push` // запушить текущую ветку в удаленную ветку.  
`git push <remote> <branch>` // запушить ветку в указанный репозиторий и удаленную ветку. (origin master / HEAD)  
`git push <remote> :<branch>` // в удаленном репозитории удалить заданную ветку.  
`git push -u origin master` // если удаленная ветка не установлена как отслеживаемая, то сделать ее такой.  
`git push -f origin HEAD` // перезаписать удаленный репозиторий локальным.  
`git push origin --delete <branch>` // удаление удаленной ветки.  
`git fetch` // загружает коммиты, файлы и ссылки из удаленного репозитория локальный репозиторий  
`git fetch <remote>` // загрузить всю историю с заданного удаленного репозитория.  
`git merge` // слияние одной или нескольких веток в текущую.  
`git merge <branch>` // соединить изменения в текущей ветке с изменениями из заданной.  
`git merge --no-ff <branch>` // соединить ветки без режима “fast forwarding”.  
`git merge <remote>/<branch>` // слить изменения локальной ветки и заданной удаленной.  
`git pull` // загрузить историю и изменения удаленной ветки и произвести слияние с текущей веткой. (fetch + merge)  
`git pull <remote> <branch>` // указать конкретную удаленную ветку для слияния.  
`git branch` // список всех локальных веток в текущей директории.  
`git branch <branchName>` // создать новую ветку.  
`git branch -a` // посмотреть полный список локальных и удаленных веток.  
`git branch -d <branch>` // удалить заданную ветку.  
`git branch -D <branch>` // принудительно удалить заданную ветку, игнорируя ошибки.  
`git branch -m <oldName> <newName>` // переименовать ветку.  
`git branch -v` // последний коммит на каждой из веток.  
`git branch --merged / --no-merged` // показать все ветки, слияние для которых было выполнено/не выполнено   
`git checkout` // переключение между ветками.  
`git checkout -b <branchName>` // создать новую ветку и переключиться на нее.  
`git checkout <branchName>` // переключиться на указанную ветку и обновить рабочую директорию.  
`git checkout -b <branchName> <remote>/<branch>` // создание новой ветки на основе удаленного репозитория.  
`git checkout <fileName>` // вернуть файл в первоначальное состояние если он еще не был добавлен в индекс коммита.  
`git checkout -- .` // сброс изменений в рабочей директории (красные коммиты).  
`git checkout <commit>` // переключение на конкретный коммит (состояние Detached HEAD).  
`git diff` // показать изменения в файлах, которые еще не были добавлены в индекс коммита (staged)..  
`git diff --staged` // показать что было добавлено в индекс с помощью git add, но еще не было закоммиченно.  
`git diff HEAD` // показать что изменилось с последнего коммита.  
`git diff HEAD^` // показать что изменилось с предпоследнего коммита.  
`git diff <branch>` // сравнить текущую ветку с заданной.  
`git diff <fileBranch>..<secondBranch>` // посмотреть различия между двумя заданными ветками.  
`git diff --stat` // показать статистику какие файлы были изменены и как.  
`git difftool -d` // то же самое, что и diff, но показывает изменения в заданной difftool.  
`git difftool -d master..` // показать изменения, сделанные в текущей ветке.  
`git rm <file>` // удалить файл из рабочей директории и добавить в индекс информацию об удалении (зеленые коммиты).  
`git rm --cached <file>` // удалить файл из репозитория, но сохранить его локально (красные коммиты).  
`git reset` // убрать изменения из индекса коммита, сами изменения останутся.  
`git reset <commit/tag>` // отменить все коммиты после указанного коммита, изменения будут сохранены локально.  
`git reset --hard <commit>` // принудительно вернутся к указанному коммиту, не сохраняя историю и изменения.  
`git reset <file>` // убрать файлы из индекса коммита (изменения не теряются).  
`git reset .` //  убрать изменения из индекса всех коммитов, сами изменения останутся (зеленые коммиты).  
`git reset --soft / --hard HEAD^1` // отменить последний коммит с сохранением изменений / без сохранения.  
`git cherry-pick <commit>` // копирование коммита в другую ветку.  
`git reflog --date=iso` // журнал ссылок с отображением даты (.git/logs/refs/heads/. и .git/logs/HEAD).  
`git stash` // положить во временное хранилище все отслеживаемые файлы.  
`git stash pop` // восстановить последние файлы, положенные во временное хранилище.  
`git stash list` // список всех сохраненных изменений во временном хранилище.  
`git stash drop` // удалить последние файлы, положенные во временное хранилище.  
`git stash apply` // применить изменения к рабочей копии, не удаляя их из набора отложенных изменений.  
`git stash clear` // удалить все наборы отложенных изменений.  
`git rebase -i` // переместить ветку в начало другой ветки в интерактивном режиме (--interactive).  
`git rebase --onto <newBase> <oldBase>` // переместить ветку начиная с определенного коммита.  
`git revert <commit>` // отмена изменений коммита и добавление нового коммита с изменениями (диапазон 88a853a^..72f4ed9).  
`git restore --staged .` // убрать все из stage (зеленые коммиты).  
`git status` // полный список изменений файлов, ожидающих коммита.  
`git status -s` // краткий вид изменений.  
`git ls-files --other --ignored --exclude-standard` // список всех игнорируемых файлов.  
`git log` // список изменения текущей ветки.  
`git log --follow <file>` // список изменения текущего файла, включая переименования.  
`git log --pretty=format:"%h %s" --graph` // изменение вида отображения истории изменений.  
`git log --author='Name' --after={1.week.ago} --pretty=oneline --abbrev-commit` // посмотреть над чем работал заданный пользователь последнюю неделю.  
`git log --no-merges master..` // посмотреть историю изменений только для текущей ветки.  
`git show <commit>` // показать метадату и изменения в заданном коммите.  
`git show <branch>:<file>` // посмотреть на файл в другой ветке, не переключаясь на неё.  
`git remote` // посмотреть список доступных удаленных репозиториев.  
`git remote -v` // посмотреть детальный список доступных удаленных репозиториев.  
`git remote add <remote><url>` // добавить новый удаленный репозиторий.

---

#### Перезаписать локальный репозиторий на удаленный с сохранением данных в новую ветку.
`git checkout master` // перейти на ветку master и обновить ее.  
`git branch newBranch` // создать новую ветку.  
`git fetch --all` // загрузить последнюю версию файлов с сервера без merge и rebase.  
`git reset --hard origin/master` // заменить все локальные файлы на удаленные.

---

### Установка Git
https://gitforwindows.org/   
https://git-scm.com/book/ru/v2/Введение-Установка-Git

`git --version`

### Генерация ключа MSysGit для GitHub
`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`  
`eval "$(ssh-agent -s)"`  
`ssh-add ~/.ssh/id_rsa`  
`clip < ~/.ssh/id_rsa.pub`  
`ssh -T git@github.com`

### Подгрузка репозитория GitHub в IDEA
`git init`  
`git remote add origin SSH_GIT_PROJECT`  
`git remote -v`  
`git checkout -b master`  
`git fetch`

### Настройки Git в IDEA
Файл **.gitignore**  
`*.class`  
`target/`  
`*.iml`  
`.idea/`

### Локальный конфиг
`C:\Users\Admin\IdeaProjects\education\.git\config`

###Глобальный конфиг
`C:\Program Files\Git\etc\gitconfig`

### Настройка Alias консоль
`git config --global alias.co checkout`  
`git config --global alias.br branch`  
`git config --global alias.ci commit`  
`git config --global alias.st status`  
`git config --global alias.ls "log --oneline --graph --decorate --all"`  
`git config --global alias.lsf "log --oneline --graph --decorate --all --pretty=format:'%C(auto)%h%d %C(reset)%s %C(green)(%cD)%C(reset) %C(blue)<%an>'"`  
`git config --global alias.rf reflog --date=iso`  
`git config --global alias.cim commit -m`

### Настройка Alias файл
`C:\Users\Admin\.gitconfig`

`co = checkout`  
`br = branch`  
`ci = commit`  
`st = status`  
`ls = log --oneline --graph --decorate --all`  
`lsf = log --oneline --graph --decorate --all --pretty=format:'%C(auto)%h%d %C(reset)%s %C(green)(%cD)%C(reset) %C(blue)<%an>'`  
`rf = reflog --date=iso`  
`cim = commit -m`

### Конфигурационные команды
`git config --global user.name "name"` // установить имя, которое будет прикрепляться к коммиту.  
`git config --global user.email "email address"` // установить email, который будет прикрепляться к коммиту.  
`git config --global color.ui auto` // включить полезную подсветку командной строки.  
`git config --global push.default current` // обновлять удаленную ветку с таким же именем, что и локальная, при пуше изменений (если не указано иного).  
`git config --global core.editor <editor>` // установить редактор для редактирования сообщений коммита.  
`git config --global diff.tool <tool>` // установить программу для разрешения конфликтов при слиянии.

### Нотации (~ и ^)

![notations](/img/notations.png)

HEAD\~ — это сокращенная запись HEAD\~1 и означает первого родителя коммита. HEAD\~2 означает первого родителя у первого родителя коммита. HEAD\~n можно понимать как «n коммитов перед HEAD» или «n-ый предок HEAD».

HEAD^ (или HEAD^1) тоже означает первого родителя коммита. Но вот HEAD^2 означает второго родителя коммита. Помните, коммит, представляющий собой нормальное слияние (merge), имеет двух родителей: первый родитель — это коммит, в который осуществляется слияние, а второй родитель — коммит, который был слит. Вообще говоря, слияния могут иметь произвольно много родителей (octopus merges).

Операторы ^ и \~ могут выстраиваться в линию, например, HEAD\~3^2 будет означать второго родителя предка HEAD третьего уровня; HEAD^^2 — второго родителя первого родителя HEAD; HEAD^^^ — это просто эквивалент HEAD\~3.
