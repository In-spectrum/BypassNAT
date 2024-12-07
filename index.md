<h1 align="center">
  <img src="manual/images/baner.bmp" alt="FaNAT" width="900" height="300">
  <br>
  Система удаленного доступа к устройствам.
</h1>

<br>

**Features**
* удаленный доступ к устройствам, которые находятся в сети, где используется NAT;
* использование собственного сервера для:
  * управления устройствами;
  * обмена файлами;
  * захвата, трансляции и просмотра рабочего стола; 
* настройка ssh-туннеля и доступ к устройству по ssh-протоколу;
* развертывание на АРМ;
  
<br>
  Поддержка: х86-64 - Windows, Ubuntu; ARM - РасбериПи, НВидиа-ТХ2

## Table of contents

* [FaNAT-server](#fanat-server)
  * [Функции](#functions)
  * [Установка](#install)
  * [Параметры запуска](#start-property)
* [Video-server](#video-server)

## FaNAT-server
### Functions
 - поиск доступных устройств, обмен данными между ними;
   
### Install
 - загрузите архив приложения  соответствующий вашей ОС и разархивируйте. Url;
 - запустите сервер: **_./FaNATServer.sh_** - для Ubuntu или **_FaNATServer.ехе_** - для Windows;

### Start property
**-pas** - set server password (по умолчанию 1111);
```
   ./FaNATServer.sh -pas 2227
```
**-p** - set listen port;
```
   ./FaNATServer.sh -p 1675
```
**-la** - время для отключения клиентов с низкой активность;
```
   ./FaNATServer.sh -la 60
```
*_если клиент подключён и не используется - он будет отключен от сервера через 60сек.<br>
Через 30сек. клиент переподключится к серверу для его повторного определения в сети._

 ## Video-server
 _***используется сторонне ПО**_<br>
 
 **Features**<br>
 Публикация и трансляция видеопотока рабочего стола управляемого устройства.

Например:
- <a href="https://github.com/bluenviron/mediamtx/tree/main" target="_blank">mediamtx</a> - доступно RTSP, RTMP.... протоколы;
- [mediamtx](https://github.com/bluenviron/mediamtx/tree/main "title" target="_blank") - доступно RTSP, RTMP.... протоколы;
	- Развёртывание - url.
 	-  Настройка - url. 
- Nginx-RTMP - url. Настройка RTMP - url.  Доступен только RTMP-протокол.
Или другой RTSP, RTMP сервер...

Установка видео-сервера не нужна, если на управляемом устройстве используется версия клиента FaNATClient-Lite (url) или FaNATClient-okl (url).
Установка видео-сервера нужна, если планируете делать захват(трансляцию) рабочего стола - используется версия клиента FaNATClient (url) и FaNATClient-console (url).



