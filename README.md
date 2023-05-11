<h3> Шпаргалка Ubuntu для начинающих </h3>
Описание. Краткий справочник некоторых команд. <br>
Может быть полезно для тех, кто только только переходит с Windows, <br>
попробовать Linux и его терминал. Сделано на основе Ubuntu 22.04.2 LTS <br>
Вы можете скопировать данный проект и пополнять его своими <br> 
примерами, командами, наблюдениями по мере необходимости<br><br>

<details>
<summary>Примечание: информация о проекте</summary>
Большая часть информация о проекте: примечания, описания, 
объяснения, картинки, комментарии <br> 
находятся в папке <b><a href="01_info">01_info</a></b>. 
</details>

<details>
<summary>Разное</summary>
<b>Установка и удаление программ с помощью графического интерфейса</b> <br>
(аналог Установка и удаление программ, программы и компоненты в Windows) <br>
Иконка (программа) называется Ubuntu software и выглядит вот так: <br>
<img alt="" src="/01_info/ubuntu_software.png"> <br>
Представляет собой хранилище программ как в интернете, так и на локальном <br>
компьютере, аналогично хранилищам в Windows или плагинам для Google Chrome <br><br>

<b>Самый простой вызов терминала</b>  <br>
Кликаем правой кнопкой на рабочем столе и вызываем Терминал <br><br>

<b>Переключение в полностью текстовый режим</b>  <br>
CTRL(левый)+ALT(левый)+(от F1 до F6) <br>
Возврат обратно в графический режим - ALT+F2 <br><br>

<b>Обычное приглашение в терминале</b>  <br>
Может быть, к примеру, таким: <br>
`user1@ubuntu:~$ `<br>
где: <br>
user1 - текщий пользователь, с которым (под которым) вы работаете в системе <br>
ubuntu - название компьютера (хоста), на котором вы сейчас находитесь <br>
~ - означает, что вы находитесь в домашней папке home данного юзера  <br><br>

<b>clear</b> <br>
`user1@ubuntu:~$ clear` <br>
Моя любимая команда, очищает экран терминала, аналог команды cls в Windows <br><br>

<b>PATH</b> <br>
`user1@ubuntu:~$ echo $PATH` <br>
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin: <br>
/usr/games:/usr/local/games:/snap/bin:/snap/bin <br>
Аналог переменной PATH в Windows, в которой отображаются <br>
пути к исполняемым файлам, что позволяет запускать эти файлы <br>
без полного указания пути к ним <br><br>

<b>Процессы и память</b> <br>
`user1@ubuntu:~$ ps` <br>
Можно посмотреть какие процессы сейчас запущены у данного пользователя <br>
Для прерываения процессов используется CTRL+C <br>
Для остановки процессов обычно используется CTRL+Z <br>
`user1@ubuntu:~$ fg` <br>
Продолжить выполнение процесса <br><br>

`user1@ubuntu:~$ top`<br>
более продвинутая команда, которая позволяет выводить информацию о системе<br>
а также список процессов, динамически обновляя информацию о потребляемых ими <br>
ресурсах (некий аналог task manager в Windows). Shift+P - сортировка процессов <br> 
по использованию процессора, Shift+M - сортировка по занимаемой памяти <br><br>

`user1@ubuntu:~$ free -h`<br>
Различная информация по памяти, -h - лучше воспринимается человеком <br><br>

<b>Логи</b> <br>
<pre>
user1@ubuntu:~$ cd /var/log
user1@ubuntu:/var/log$ ls
alternatives.log    dmesg.0          openvpn
alternatives.log.1  dmesg.1.gz       private
apport.log          dmesg.2.gz       speech-dispatcher
...
</pre>
Все основные логи хранятся здесь.<br><br>

</details>

<a href="/01_info/help/HELP_COMMANDS.md">Разная помощь по командам -</a> <br> 
как правильно набрать команду, какие команды существуют, <br> 
описания, ключи и т.д.

<a href="/01_info/info/INFO.md">Разная справочная информация -</a> <br>
о процессоре, ОС, времени и т.д. <br>

<a href="/01_info/fs/FS.md">Файловая система - общая информация -</a> <br>
Особенности, примечания, корневая структура <br>

<a href="/01_info/fs/FILE.md">Файловая система - файлы -</a>  <br>
Некоторые команды работы с файлами <br><br>

<a href="/01_info/fs/DIR.md">Файловая система - каталоги -</a> <br>
Отдельные команды для работы с директориями (папками)<br>

<details>
<summary>Примечание: спасибо</summary>
Спасибо вам за проявленный интерес к проекту.
Надеюсь проект дал вам что-то полезное.
</details>