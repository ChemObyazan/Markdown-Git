#Git. Публикация на удалённом репозитории
Перед импортом данных на удалённый депозиторий необходимо:
1. Создать удалённый репозиторий (Например на Github)
2. Связать удалённый репозиторий с локальным
3. Настроить SSH подключение

Инструкция, как выполнить 1 и 2 пункты, описана в главе [Git. Создание и управление репозиторием](./Git.%20%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%B8%20%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5%20%D1%80%D0%B5%D0%BF%D0%BE%D0%B7%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B5%D0%BC.md)

Что такое SSH? SSH - это специальный идентификатор, своего рода ключ-подпись, который предоставляет право вносить изменение в репозиторий.
Создаётся с помощью команды:
`ssh-keygen`
После введения команды, ключ создастся автоматически, в виде файла в папке пользователя. Нужно нажать ENTER для подтверждения создания файла.
```
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/1/.ssh/id_rsa):
Created directory '/c/Users/1/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/1/.ssh/id_rsa
Your public key has been saved in /c/Users/1/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:YIQ2tA+b09uZ70pmJ0TTQaxxt0P5p62kVN0BUBGBrtE 1@DESKTOP-TMFAGVT
The key's randomart image is:
+---[RSA 3072]----+
|   ....  oo.+B=  |
|    +o  ..oo+  . |
|   .o.o o++o o .o|
|     B o.o Eo o +|
|    + o S o  o + |
|     . + +  . o .|
|      . O .. o . |
|       + +  . .  |
|        .oo      |
+----[SHA256]-----+

```

Далее необходимо скопировать содержимое файла `/c/Users/1/.ssh/id_rsa.pub` и сохранить в настройках Github
![ssh](./ssh.PNG)

Процесс предварительной настройки окончен. Теперь можно импортировать коммиты с локального репозитория на удалённый.
Команда
`git push`
