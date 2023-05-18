<a href="/README.md">вернуться к оглавлению</a>

<b>Аккаунты Linux</b> <br><br>

В Ubuntu есть 2 основных типа аккаунта для пользователей: Администратор и Стандартный.<br>
Отличия между ними в том, что администратор может использовать <br>
режим (привилегии) суперпользователя (sudo), а обычный пользователь - нет.<br>
Кроме этого в системе есть аккаунт Root - корневой (системный)<br><br>

<b>Id пользователя</b> <br>
`user1@ubuntu:~$ id` <br>
`uid=1000(user1) gid=1000(user1) groups=1000(user1),999(vboxsf)`<br>
Команда id выводит id текущего пользователя, id его группы, и группы, в которых он состоит<br>
`user1@ubuntu:~$ id имя_пользователя` <br>
Выводит информацию ту же информацию о любом пользователе <br><br>

<b>Подключение sudo для повышения прав</b> <br>
Для многих операций необходимо повысить права текущего пользователя.<br>
Один из способов это сделать - добавить пользователя в группу sudo или wheel <br>

~ Проверяем наличие соответствующих групп <br>
`user1@ubuntu:~$ cat /etc/group | sort` <br>
можно просто вывести в терминал список групп в сортированном виде и посмотреть <br>

`user1@ubuntu:~$ cat /etc/group | grep sudo`<br>
можно попробовать найти группу и вывести только её <br>

~ Используем права суперпользователя root и открываем консоль под ним.<br>
`user1@ubuntu:~$ su`<br>
Password: (ваш пароль) <br>
Вывод:<br>
`root@ubuntu:/home/user1#` <br>

~ Добавляем своего пользователя в группу которую нашли <br>
`root@ubuntu:/etc# sudo adduser user1 sudo` <br>

~ Выходим из аккаунта суперпользователя (возвращаемся в свой аккаунт)<br>
`root@ubuntu:/etc# exit` <br>

~ Проверяем свои права <br>
`user1@ubuntu:/etc$ su - user1` <br>
Password: (вводим свой пароль) <br>
Вывод: <br>
To run a command as administrator (user "root"), use "sudo <command>". <br>
See "man sudo_root" for details. (все нормально) <br>

~ Проверяем свое присутствие в группе sudo <br>
`user1@ubuntu:~$ groups `<br>
Вывод: <br>
`user1 sudo vboxsf `<br><br>

<b>Папки пользователей</b> <br>
<pre>
user1@ubuntu:~$ cd /home
user1@ubuntu:/home$ ls -l
total 4
drwxr-x--- 16 user1 user1 4096 мая 11 18:46 user1
</pre>
Все папки пользователей сохраняются в папке /home<br><br>

<b>Записи об аккаунтах</b> <br>
<pre>
user1@ubuntu:/home$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
...
user1:x:1000:1000:user1,,,:/home/user1:/bin/bash
vboxadd:x:999:1::/var/run/vboxadd:/bin/false
</pre>
Запись обо всех аккаунтах хранится по адресу: /etc/passwd<br>

Частичная расшифровка: <br>
`user1:x:1000:1000:user1,,,:/home/user1:/bin/bash`<br>
user1 - имя пользователя <br>
x - пароль сохранятся отдельно <br>
1000 - id пользователя <br>
1000 - группа этого пользователя <br>
/home/user1 - домашняя папка <br>
/bin/bash - какая shell (оболочка) должна использоваться по умолчанию <br><br>

<b>Файл паролей</b> <br>
<pre>
user1@ubuntu:~$ sudo cat /etc/shadow
root:$y$j9T$AQSeKDFkmbe1VKqFmprPl0$aESrVyMNoeC57oNdbTQeWwruIXvr.LilsgbJNuCNXI5:19467:0:99999:7:::
daemon:*:19411:0:99999:7:::
bin:*:19411:0:99999:7:::
sys:*:19411:0:99999:7:::
sync:*:19411:0:99999:7:::
games:*:19411:0:99999:7:::
man:*:19411:0:99999:7:::
...
user1:$y$j9T$0LyTAXQRaAj7dztPnxKqP/$eaxD8/S.SvAG2rQ2FSJkCKt5qx1BM9RoMHi..cTAUV2:19467:0:99999:7:::
vboxadd:!:19467::::::
</pre>
файл паролей находится в /etc/shadow в зашифрованном виде, <br>
доступ к нему идет только через sudo. Даже если у пользователей пароли <br> 
одинаковые - в зашифрованном виде они будут выглядеть по разному.<br><br>

<b>Вход в систему</b> <br>
`user1@ubuntu:~$ last`<br>
С помощью команды last можно посмотреть последние входы в систему, когда были,<br> 
под каким пользователем<br>

`user1@ubuntu:~$ who`<br>
`user1    tty2         2023-05-11 18:46 (tty2)`<br>
Команда who позволяет посмотреть, кто сейчас находится в системе,<br> 
и работает вместе с вами. Еще больше информации дает команда "w"<br><br>

<b>Добавление и удаление пользователя</b> <br>
<pre>
user1@ubuntu:~$ sudo useradd -m user2
[sudo] password for user1: пароль 
user1@ubuntu:~$ ls -l /home
total 8
drwxr-x--- 16 user1 user1 4096 мая 17 04:59 user1
drwxr-x---  2 user2 user2 4096 мая 18 01:05 user2
</pre>
Через sudo добавляем нового пользовтеля user2 и "-m" создаем ему домашнюю папку.<br> 
Далее проверяем созданного пользователя. Пока он не может входить в систему <br>
т.к. у него нет пароля.<br>
<pre>
user1@ubuntu:~$ sudo passwd user2
New password: пароль
Retype new password: повторяем пароль
passwd: password updated successfully
</pre>
Добавляем (обновляем) пароль для юзера <br>

`user1@ubuntu:~$ sudo userdel -r user2`<br>
Удалить пользователя и все папки, которые для него были созданы<br><br>















 





