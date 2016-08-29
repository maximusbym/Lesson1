# Lesson1
Lesson1 - networks &amp; local environment

##XAMPP
<p>
1. Скачайте и установите XAMPP: <a href="https://www.apachefriends.org/ru/index.html">https://www.apachefriends.org/ru/index.html</a>
</p>
<p>
2. Настройте виртуальные хосты: в низ файла <i>xampp\apache\conf\extra\httpd-vhosts.conf</i> добавьте содержимое файла репозитория <i>httpd-vhosts.conf</i> c заменой путей расположения XAMPP и файлов сайта на вашей системе.
</p>
<p>
3. Добавте новый виртуальный хост в файл <i>hosts</i> Windows: <i>C:\windows\system32\drivers\etc\hosts</i>. Например:
</p>
```
...
127.0.0.1     lesson1.local
127.0.0.1     www.lesson1.local
```
<p>
4. Для устранения ограниченния <i>403 Error. Permission denied for custom host</i>. В файл <i>xampp\apache\conf\httpd.conf</i> добавьте указанный фрагмент кода с заменой путя к файлам сайтов на вашей системе:
</p>
```
<Directory D://Projects/>
    AllowOverride none
    Require all granted
</Directory>
```
<p>
5. Установите заглушку для отправки писем:
<br/>
5.1 Скопируйте файл репозитория <i>sendmail.php</i> в <i>xampp/sendmail/sendmail.php</i>
<br/>
5.2. В файле <i>xampp/php/php.ini</i> добавьте строку:
</p>
```
sendmail_path = D:\xampp\php\php.exe D:\xampp\sendmail\sendmail.php
```
##Homestead
<p>
1. Ограничения и подготовка:
</p><p>
1.1. Оригинальная сборка только для х64 систем.
</p><p>
1.2. под Windows, если ваше имя пользователя содержит кириллицу (например «Вася»), то предварительно нужно выполнить команду:
</p>
```
chcp 1251
```
<p>
1.3. Нужно создать ssh ключ для запуска и подключения к виртуальной машине. В GIT консоле:
</p>
```
ssh-keygen -t rsa -C "your@email.com"
```
<p>
1.3.1. Для доступа в GIT консоль нужно установить GIT и использовать CLI Git Bash для команд: <a href="https://git-scm.com/">https://git-scm.com/</a>
</p>
<p>
2. Далее следуйте детальной инструкции по ссылке: <a href="https://laravel.com/docs/5.3/homestead#installation-and-setup">https://laravel.com/docs/5.3/homestead</a>
</p>
