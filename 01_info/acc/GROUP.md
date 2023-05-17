<a href="/README.md">вернуться к оглавлению</a>

<b>Группы пользователей Linux</b> <br><br>

Основа распределения прав доступа в операционной системе Linux лежит на понятии <br> 
пользователь. Пользователю-владельцу файла выдаются определенные полномочия для <br> 
работы с ним, а именно на чтение, запись и выполнение. Также отдельно устанавливаются <br> 
полномочия на чтение, запись и выполнение для всех остальных пользователей. <br> 
Поскольку в Linux все есть файл, то такая система позволяет регулировать доступ <br> 
к любому действию в этой операционной системе с помощью установки прав доступа на <br>
файлы. Но еще при создании Linux, разработчики поняли, что этого явно недостаточно.<br><br>

Поэтому и были придуманы группы пользователей. Пользователи могут объединяться в группы, <br> 
чтобы уже группам выдавать нужные полномочия на доступ к тем или иным файлам, а <br> 
соответственно и действиям. В этой статье мы рассмотрим группы пользователей в Linux, <br> 
рассмотрим зачем они нужны, как добавить пользователя в группу и управлять группами.<br><br>

<b>Группы</b> <br><br>

<pre>
user1@ubuntu:~$ cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:syslog
tty:x:5:
...
user1:x:1000:
...
docker:x:997:

</pre>
Все группы, созданные в системе, находятся в /etc/group<br><br>

<b>Описание некоторых групп</b> <br><br>
**daemon** - от имени этой группы и пользователя daemon запускаются сервисы, <br> 
которым необходима возможность записи файлов на диск.<br>
**sys** - группа открывает доступ к исходникам ядра и файлам include сохраненным <br> 
в системе <br>
**sync** - позволяет выполнять команду /bin/sync <br>
**games** - разрешает играм записывать свои файлы настроек и историю в определенную <br> 
папку
**man** - позволяет добавлять страницы в директорию /var/cache/man <br>
**lp** - позволяет использовать устройства параллельных портов <br>
**mail** - позволяет записывать данные в почтовые ящики /var/mail/ <br>
**proxy** - используется прокси серверами, нет доступа записи файлов на диск <br>
**www-data** - с этой группой запускается веб-сервер, она дает доступ на запись /var/www, <br> 
где находятся файлы веб-документов <br> 
**list** - позволяет просматривать сообщения в /var/mail <br>
**nogroup** - используется для процессов, которые не могут создавать файлов <br> 
на жестком диске, а только читать, обычно применяется вместе с пользователем nobody. <br>
**adm** - позволяет читать логи из директории /var/log <br>
**tty** - все устройства /dev/vca разрешают доступ на чтение и запись пользователям <br> 
из этой группы <br>
**disk** - открывает доступ к жестким дискам /dev/sd* /dev/hd*, можно сказать, что это <br> 
аналог рут доступа. <br>
**dialout** - полный доступ к серийному порту <br>
**cdrom** - доступ к CD-ROM <br>
**wheel** - позволяет запускать утилиту sudo для повышения привилегий <br>
**audio** - управление аудиодрайвером <br>
**src** - полный доступ к исходникам в каталоге /usr/src/ <br>
**shadow** - разрешает чтение файла /etc/shadow <br>
**utmp** - разрешает запись в файлы /var/log/utmp /var/log/wtmp <br>
**video** - позволяет работать с видеодрайвером <br>
**plugdev** - позволяет монтировать внешние устройства USB, CD и т д <br>
**staff** - разрешает запись в папку /usr/local <br><br>


<b>Как посмотреть владельца и группу</b> <br><br>
<pre>
user1@ubuntu:~$ ls -l
total 36
drwxr-xr-x 2 user1 user1 4096 мая 11 19:22 Desktop
drwxr-xr-x 2 user1 user1 4096 апр 20 17:38 Documents
drwxr-xr-x 2 user1 user1 4096 апр 20 17:38 Downloads
drwxr-xr-x 2 user1 user1 4096 апр 20 17:38 Music
drwxr-xr-x 2 user1 user1 4096 апр 20 17:38 Pictures
drwxr-xr-x 2 user1 user1 4096 апр 20 17:38 Public
drwx------ 5 user1 user1 4096 апр 20 18:18 snap
drwxr-xr-x 2 user1 user1 4096 апр 20 17:38 Templates
drwxr-xr-x 2 user1 user1 4096 апр 20 17:38 Videos
</pre>
В этом полном списке папок в домашней папке пользователя user1 мы видим <br>
user1 user1 - это владелец и группа к которой относятся эти папки. <br><br>

<b>Id и группа пользователя</b> <br>
`user1@ubuntu:~$ id` <br>
`uid=1000(user1) gid=1000(user1) groups=1000(user1),999(vboxsf)`<br>
Команда id выводит id текущего пользователя, id его группы, и группы, в которых он состоит<br>
`user1@ubuntu:~$ id имя_пользователя` <br>
Выводит информацию ту же информацию о любом пользователе <br><br>

`user1@ubuntu:~$ groups`<br>
`user1 vboxsf`<br>
Также отдельно можно посмотреть группы, в которых состоит пользователь<br>
`user1@ubuntu:~$ groups | wc -w` <br>
`2` <br>
или посчитать их количество

`user1@ubuntu:~$  chgrp имя_группы имя_файла`<br>
Есть возможность поменять группу вручную командой chgrp










