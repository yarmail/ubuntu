<a href="/README.md">вернуться к оглавлению</a>

<b>Разная помощь (по командам)</b> <br><br>

<b>man -k</b><br>
user1@ubuntu:~$ man -k time <br>
__ppc_get_timebase (3) - get the current value of the Time Base Register o...<br>
__ppc_get_timebase_freq (3) - get the current value of the Time Base Regis... <br>
adjtime (3)          - correct the time to synchronize the system clock <br>
adjtime_config (5)   - information about hardware clock setting and drift ... <br>
adjtimex (2)         - tune kernel clock <br>
... <br>
Вывести список всех команд в названии или в описании которых есть слово time <br>
Такая команда хорошо подходит для случаев, когда вы плохо помните название команды <br>
но примерно представляете, что там надо делать (знаете ключевые слова)<br><br>

<b>man</b><br>
user1@ubuntu:~$ man uptime <br>
<pre>UPTIME(1)                      User Commands                      UPTIME(1)

<b>NAME</b>
       uptime - Tell how long the system has been running.

<b>SYNOPSIS</b>
       <b>uptime</b> [<u style="text-decoration-style:solid">options</u>]

<b>DESCRIPTION</b>
</pre>
Полный мануал по указанной команде во вьювере. Описание можно прокручивать <br>
колесом мыши или кнопками управления курсором. <br>
Для поиска слов в описании можно использовать такую конструкцию: <br>
набираем "/слово" и Enter, <br> 
клавиша "n" используется для поиска следующего вхождения<br>
слова (словосочетания), "q" - для выхода из просмотра. <br><br>

<b>info</b><br>
user1@ubuntu:~$ info uptime <br>
Другой вариант получения информации о команде <br><br>

<b>whatis</b><br>
user1@ubuntu:~$ whatis uptime <br>
uptime (1)  - Tell how long the system has been running. <br>
Короткий вариант описания о команде <br><br>

<b>whereis</b><br>
user1@ubuntu:~$ whereis uptime <br>
uptime: /usr/bin/uptime /usr/share/man/man1/uptime.1.gz <br>
Где находится (адрес) программа (команда) и её документация<br>
Другой вариант этой команды:<br>
user1@ubuntu:~$ locate uptime <br><br>

<b>Помощь при наборе команд</b>  <br>
В некоторых случаях, если вы набираете команду и не помните как её точно набирать, <br>
вы можете нажать клавишу Tab и, если у ОС есть варианты продолжения <br>
команды, она может их добавить в строку (некая форма автодополнения или T9)<br><br>