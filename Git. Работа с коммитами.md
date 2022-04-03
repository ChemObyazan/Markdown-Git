#Git. Работа с коммитами
##Добавление коммита в репозиторий

После добавления файлов в коммит необходимо создать коммит
Коммит создается с помощью команды
`git commit`

после запуска указанной команды откроется редактор коммита.
```
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
#
# Initial commit
#
# Changes to be committed:
#	new file:   .gitignore
```
Редактировать текст в открывшемся редакторе можно после нажатии клавиши **i**
Прописываем комментарий в верхней части коммита
```
Это мой первый коммит. Добавлена первая часть инструкции
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
#
# Initial commit
#
# Changes to be committed:
#	new file:   .gitignore
```

Для завершения редактирования необходимо нажать клавишу **Esc**
Для выхода из редактора нужно ввести **:wq**

Команда 
`git commit -m 'текст коментария коммита'`
сразу создает коммит с необходимым комментарием

Команда 
`git commit -a`
сразу создает коммит с новыми изменениями ранее отслеживаемых файлах репозитория

Команда 
`git commit -am 'текст комментария коммита'`
сразу создает коммит с новыми изменениями ранее отслеживаемых файлах репозитория и необходимым комментарием