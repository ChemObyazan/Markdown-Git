#Git. Управление измениями
### История коммитов репозитория
Git содержит встроенные инструменты просмотра истории внесённых изменений (коммитов).

Команда `git log` покажет всю **историю созданных коммитов** текущей ветки данного репозитория. Например
```
1@DESKTOP-TMFAGVT MINGW64 /d/task 1.13 (master)
$ git log
commit 2865d3f9c1c2beafa5174f05a29ccd135438cec8 (HEAD -> master)
Author: ChemObyazan <rusl92@inbox.ru>
Date:   Thu Mar 31 01:20:20 2022 +0300

    add 2 new files. work with commits

commit cba2cc6268ec69ff825002dca33bb94874a737b2
Author: ChemObyazan <rusl92@inbox.ru>
Date:   Thu Mar 31 01:10:58 2022 +0300

    new portion files

commit 31e5d86ccd9649f026911d3cae167e24cb91290c
Author: ChemObyazan <rusl92@inbox.ru>
Date:   Mon Mar 28 03:10:40 2022 +0300

    add basic files


```
где `31e5d86ccd9649f026911d3cae167e24cb91290c` является уникальным идентификационным номером коммита.

Когда в репозитории было создано слишком много коммитов, просматривать историю с помощью команды `git log` неудобно. Для более лаконичного представления используется команда `git log --oneline`. 
```
1@DESKTOP-TMFAGVT MINGW64 /d/task 1.13 (master)
$ git log --oneline
2865d3f (HEAD -> master) add 2 new files. work with commits
cba2cc6 new portion files
31e5d86 add basic files
```
Так же существует отдельная команда которая показывает не только историю создания коммитов, а **историю всех операций** производимых в текущей ветке репозитория.
Команда `git reflog`

###Удаление коммита
Бывают случаи когда ранее созданный коммит необходимо удалить.
Для этого используется команда `git reset уникальный идентификационный номер коммита сделанного ПЕРЕД удаляемым коммитом` 

Например, если необходимо удалить 2 последних коммита то следует ввести:
`git reset 31e5d86ccd9649f026911d3cae167e24cb91290c` или `git reset 31e5d86`
На самом деле коммит удаляется не полностью из репозитория и его всегда можно восстановить

###Восстановление коммита
По своей сути команда `git reset` ничего не удаляет , а делает активным содержание репозитория на редакцию коммита хеш которой указан в операции. Например, в примере про удаление коммита был ввёден хеш (индивидуальный идентификационный номер) первого коммита. Таким образом, измения содержащиеся в последующих двух коммитах не учитывались в текущей версии репозитория. соответственно если необходимо отменить "удаление" коммита то необходимо ввести хэш последнего хронологически созданного коммита. Например:
`git reset 2865d3f9c1c2beafa5174f05a29ccd135438cec8` или `git reset 2865d3f`

###Отмена коммита
Команда `git revert`.
Чем же отличается `git revert` от `git reset` ?
`git revert` **отменяет действие** какого-либо предыдущего коммита **создавая при этом новый коммит**, в то время как **`git reset` изменяет текущее состояние репозитория на момент указываемого коммита**. 
Например, 
первым коммитом было создано 10 файлов в проекте
вторым коммитом, еще +5
команда `git reset хеш 1-го коммита` - откатит количество файлов в проекте до 10 вместо 15
команда `git revert хеш 1-го коммита` - отменит действие первого коммита по добавлению 10 файлов, создав при этом третий (новый) коммит проекта содержащего 5 файлов.

