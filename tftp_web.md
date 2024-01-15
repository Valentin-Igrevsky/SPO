<h3>Задание №1</h3>

Установить и настроить TFTP-сервер, загрузить и скачать оттуда текстовый файл с содержимым на свое усмотрение.

1. Настройка файла конфигурации

<p style="text-align:center">
    <img src="tftp_web_img/1.png" alt>
</p>
<p style="text-align:center">
    <em>tftpd-hpa</em>
</p>

2. Запуск службы

<p style="text-align:center">
    <img src="tftp_web_img/2.png" alt>
</p>

3. Создание файла на сервере

<p style="text-align:center">
    <img src="tftp_web_img/3.png" alt>
</p>

4. Получение файла с сервера

<p style="text-align:center">
    <img src="tftp_web_img/4.png" alt>
</p>

5. Создание файла и загрузка его на сервер

<p style="text-align:center">
    <img src="tftp_web_img/5.png" alt>
</p>

<h3>Задание №2</h3>

Установить и настроить NGINX. Сделать так, чтобы по запросу http://<ip адрес>/main можно было скачать файл/srv/www/main, а по запросу http://<ip адрес>/main.cfg- файл/srv/www/conf/main .cfg. Содержимое файлов может быть произвольным.

1. Настройка файла конфигурации

<p style="text-align:center">
    <img src="tftp_web_img/6.png" alt>
</p>
<p style="text-align:center">
    <em>/etc/nginx/nginx.conf</em>
</p>

2. Создание директорий и файлов

<p style="text-align:center">
    <img src="tftp_web_img/7.png" alt>
</p>

3. Запуск службы

<p style="text-align:center">
    <img src="tftp_web_img/7_5.png" alt>
</p>

4. Получение файлов

<p style="text-align:center">
    <img src="tftp_web_img/8.png" alt>
</p>