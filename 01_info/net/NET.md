<a href="/README.md">вернуться к оглавлению</a>

<b>Некоторые сетевые команды</b> <br><br>

<b>ifconfig</b> <br>
Аналог команды ipconfig в Windows, в стандартной установке недоступно,<br>
но предлагает установить "command 'ifconfig' not found, but can be installed with:<br> 
sudo apt install net-tools"<br><br>

<b>ip addr show</b> <br>
Как я понимаю более новый вариант команды ifconfig, присутствует в стандартной <br> 
установке <br><br>

<b>route, ip route show</b> <br>
Команда для перенаправления пакетов, отсутствует в стандартной конфигурации, <br> 
как и ifconfig, показывает адрес шлюза, её более новый вариант - ip route show <br><br>

<b>ping</b> <br>
Пинг (адреса), такая же команда как и в Windows, только пингут постоянно. <br>
Для прерывания работы использовать CTRL+C. Дя указания количества циклов <br>
используется ключ "-с 4" - сделать пинг 4 раза. <br><br>

<b>traceroute</b> <br>
Также отсутствует в стандартной установке, как я понимаю, должна показывать <br>
маршрут движения запроса <br><br>

<b>host адрес сайта</b> <br>
показывает alias имена адресов и их ip адреса. Расширенную информацию можно <br> 
получить используя команду "dig адрес сайта"<br><br>

<b>netstat</b> <br>
По сути похожая команда netstat в Windows, показать закрытые и открытые <br> 
порты и соединения <br><br>




