<h3> Шпаргалка Ubuntu для начинающих </h3>
Описание. Краткий справочник некоторых команд. <br>
Может быть полезно для тех, кто только только переходит с Windows, <br>
попробовать Linux и его терминал. Сделано на основе Ubuntu 22.04.2 LTS <br>
Вы можете форкнуть или склонировать данный проект и пополнять его своими <br> 
примерами, командами, наблюдениями по мере необходимости<br>
Жми ★ если понравилось. <br><br>


<details>
<summary>Разное</summary>

<b>Самый простой вызов терминала</b>  <br>
Кликаем правой кнопкой на рабочем столе и вызываем Терминал <br>
или нажимаем CTRL+ALT+T<br><br>

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
Моя любимая команда, очищает экран терминала, аналог команды cls в Windows <br>
`user1@ubuntu:~$ echo $?` <br>
Можно посмотреть статус выполнения предыдущей команды, если он = 0, <br> 
значит все нормально<br><br>

<b>lsb-release</b> <br>
`user1@ubuntu:~$ cat /etc/lsb-release` <br>
Вывод:<br>
<pre>
DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=22.04
DISTRIB_CODENAME=jammy
DISTRIB_DESCRIPTION="Ubuntu 22.04.2 LTS"
</pre>
Можно посмотреть информацию о текущей ОС<br><br>

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

<b>Перезагрузка и выключение компьютера</b> <br>
Перезагрука - "sudo reboot now", <br>
Выключение - "sudo shutdown now"


</details>

<a href="/01_info/help/HELP_COMMANDS.md">Разная помощь по командам -</a> <br> 
как правильно набрать команду, какие команды существуют, <br> 
описания, ключи и т.д.

<a href="/01_info/info/INFO.md">Разная справочная информация -</a> <br>
о процессоре, ОС, времени и т.д. <br>

<a href="/01_info/fs/FS.md">Файловая система - общая информация -</a> <br>
Особенности, примечания, корневая структура <br>

<a href="/01_info/fs/FILE.md">Файловая система - файлы -</a>  <br>
Некоторые команды работы с файлами <br>

<a href="/01_info/fs/DIR.md">Файловая система - каталоги -</a> <br>
Отдельные команды для работы с директориями (папками)<br>

<a href="01_info/acc/ACC.md">Аккаунты Linux</a> <br>
Типы аккаунтов, получение прав sudo, папки пользователей и др. <br>

<a href="01_info/acc/GROUP.md">Группы пользователей Linux</a> <br>
Общее описание, описание некоторых групп, отдельные команды<br>

<a href="01_info/access/ACCESS.md">Права доступа</a> <br>
к файлам и папкам <br>

<a href="01_info/net/NET.md">Сетевые команды</a> <br>
ifconfig, route, ping и другие <br>

<a href="01_info/install/INSTALL.md">Установка программ</a> <br>
с помощью терминала или графической оболочки<br>