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
* [FaNAT-client](#fanat-client)
  * [Функции](#functions-1)
  * [FaNAT-client-fv](#fanat-client-fv)
	* [Available](#available)
  	* [Установка](#install-1)
		* [Windows](#windows)
		* [Ubuntu](#ubuntu)

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
Через 30сек. клиент переподключится к серверу для повторной идентификации в сети._

 ## Video-server
 _*используется сторонне ПО_<br>
 
 **Features**<br>
 Публикация и трансляция видеопотока рабочего стола управляемого устройства.

**Пример:**
- <a href="https://github.com/bluenviron/mediamtx/tree/main" target="_blank">mediamtx</a> - доступно RTSP, RTMP.... протоколы;
- <a href="https://www.digitalocean.com/community/tutorials/how-to-set-up-a-video-streaming-server-using-nginx-rtmp-on-ubuntu-20-04" target="_blank">Nginx-RTMP</a> - доступно RTMP-протокол;
- или другой RTSP, RTMP сервер;

**Specifications**
- установка видео-сервера не нужна, если на управляемом устройстве используется версия клиента FaNAT-client-lite (url) или FaNAT-client-okl (url).;
- установка видео-сервера нужна, если планируете делать захват(трансляцию) рабочего стола - используется версия клиента FaNAT-client (url) и FaNAT-client-console (url);

## FaNAT-client
### Functions  
  - захват, трансляция, просмотр рабочего стола (RTSP, RTMP-поток);
  - оправка, эмуляция сигналов мышки и клавиатуры;
  - отдельно, использование командной строки на управляемом устройстве. Exemple п.9.1 url;
  - возможность запустить ssh-клиент с обратным туннелем и получить доступ к устройству по ssh-протоколу. Exemple п.9.2 url;
  - обмен файлами. Файлы сохраняются в Download folder;
  - консольный вариант для использования в ваших приложениях или как дополнительная служба поддержки при запуске устройства.

### FaNAT-client-fv
**Фул-версия с пользовательским интерфейсом.**<br>
_*требуется установка [дополнительного ПО](#install-1)_

#### Available:
- поиск и управление устройствами в сети;
- захват, трансляция, просмотр рабочего стола;
- отправка сигналов мышки и клавиатуры;
- эмуляцию сигналов мышки и клавиатуры;
- отправка, выполнение инструкций в командной строке на управляемом устройстве и получение результата от него;
- обмен файлами;
- настройка качества видеопотока;
  
#### Install 
##### Windows:
- установите <a href="https://gstreamer.freedesktop.org/features/index.html" target="_blank">GStreamer</a> - url. п.8.1.1;
- загрузите <a href="https://url" target="_blank">архив приложения</a> и разархивируйте его. Запустите **_FaNATClient.ехе_**

##### Ubuntu:
- для отображения интерфейса и эмуляции сигналов клавиатуры:
```
#sudo apt-get install '^libxcb.*-dev' libx11-xcb-dev libglu1-mesa-dev libxrender-dev libxi-dev libxkbcommon-dev libxkbcommon-x11-dev -y
```
- дополнительные плагины <a href="https://gstreamer.freedesktop.org/features/index.html" target="_blank">GStreamer</a>:
```
#sudo apt-get install gstreamer1.0-plugins-ugly gstreamer1.0-plugins-bad gstreamer1.0-rtsp -y
```
- загрузите <a href="https://url" target="_blank">архив приложения</a>. В Command Line запустите **_./FaNATClient.sh_**





