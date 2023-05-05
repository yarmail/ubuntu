<a href="/README.md">вернуться к оглавлению</a>

<b>Файловая система - команды</b> <br><br>

<b>CD</b> - change directory <br>
`user1@ubuntu:~$ cd /` <br>
`user1@ubuntu:/$`<br>
Переход в корневой раздел<br> <br>

`user1@ubuntu:~$ cd ` <br>
cd без адресов и ключей - вернуться в рабочую (домашнюю) папку home <br>
(другой вариант - "cd ~")<br><br>

`user1@ubuntu:~$ cd . ` - текущая директория<br>
`user1@ubuntu:~$ cd .. `- уйти на директорию уровнем выше <br>

<b>ls</b> - list, listing <br>
`user1@ubuntu:/$ ls`
<pre>
bin    dev   lib    libx32      mnt   root  snap      sys  var
boot   etc   lib32  lost+found  opt   run   srv       tmp
cdrom  home  lib64  media       proc  sbin  swapfile  usr
</pre>
Краткое содержание, список файлов и папок в этом месте <br>

`user1@ubuntu:/$ ls -l`
<pre> 
total 2097232
lrwxrwxrwx   1 root root          7 апр 20 17:08 bin -> usr/bin
drwxr-xr-x   4 root root       4096 апр 26 06:27 boot
drwxrwxr-x   2 root root       4096 апр 20 17:14 cdrom
...
</pre>
Полное отображение списка в виде таблицы списка файлов и папок <br><br>

`user1@ubuntu:/$ ls -la` <br>
Тоже самое, включая скрытые файлы и папки <br><br>

`user1@ubuntu:/$ pwd`<br>
`/` <br>
pwd - print working directory - напечатать текущую директорию <br><br>