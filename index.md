<h1 align="center">
  <img src="manual/images/baner.bmp" alt="FaNAT" width="750" height="250">
  <br>
  Система удаленного доступа к устройствам.
</h1>

<br>

**Features**
* удаленный доступ к устройствам, которые находятся в сети, где используется NAT;
* использование собственного (или другого доступного) сервера для:
  * управления устройствами;
  * обмена файлами;
  * захвата, трансляции и просмотра рабочего стола; 
* настройка ssh-туннеля и доступ к устройству по ssh-протоколу;
* развертывание на АРМ;
  
<br>
  Поддержка: х86-64 - Windows, Ubuntu; ARM - РасбериПи, НВидиа-ТХ2

## Table of contents

* [**Video-server**](#video-server)
* [**FaNAT-server**](#fanat-server)
  * [Функции](#functions)
  * [Установка](#install)
  * [Параметры запуска](#start-property)
* [**FaNAT-client**](#fanat-client)
  * [Функции](#functions-1)
  * [**FaNAT-client-fv**](#fanat-client-fv)
	* [Available](#available)
  	* [Установка](#install-1)
		* [Windows](#windows)
		* [Ubuntu](#ubuntu)
  * [**FaNAT-client-lite**](#fanat-client-lite)
	* [Available](#available-1)
  	* [Unavailable](#unavailable)
  	* [Установка](#install-2)
		* [Windows](#windows-1)
		* [Ubuntu](#ubuntu-1)
  * [**FaNAT-client-console-cc**](#fanat-client-console-cc)
	* [Available](#available-2)
  	* [Unavailable](#unavailable-1)
  	* [Установка](#install-3)
		* [Windows](#windows-2)
		* [Ubuntu](#ubuntu-2)
   	* [Параметры запуска](#start-property-1)
  * [**FaNAT-client-console-cl**](#fanat-client-console-cl)
	* [Available](#available-3)
  	* [Unavailable](#unavailable-2)
  	* [Установка](#install-4)
		* [Windows](#windows-3)
		* [Ubuntu](#ubuntu-3)
   	* [Параметры запуска](#start-property-2)

## Video-server
 _&ensp;&nbsp;*используется сторонне ПО_<br>
 
### Features
Публикация и трансляция видеопотока рабочего стола управляемого устройства.

### Пример
- <a href="https://github.com/bluenviron/mediamtx/tree/main" target="_blank">mediamtx</a> - доступно RTSP, RTMP.... протоколы;
- <a href="https://www.digitalocean.com/community/tutorials/how-to-set-up-a-video-streaming-server-using-nginx-rtmp-on-ubuntu-20-04" target="_blank">Nginx-RTMP</a> - доступно RTMP-протокол;
- или другой RTSP, RTMP сервер;

### Specifications
- установка видео-сервера не нужна, если на управляемом устройстве используется версия клиента FaNAT-client-lite (url) или FaNAT-client-okl (url).;
- установка видео-сервера нужна, если планируете делать захват(трансляцию) рабочего стола - используется версия клиента FaNAT-client (url) и FaNAT-client-console (url);

## FaNAT-server
### Functions
- поиск доступных устройств, обмен данными между ними;
   
### Install
 - загрузите архив приложения  соответствующий вашей ОС и разархивируйте. Url;
 - запустите сервер: **_./FaNATServer.sh_** - для Ubuntu или **_FaNATServer.ехе_** - для Windows;

### Start property
**-pas** - set server password (по умолчанию 1111); _**./FaNATServer.sh -pas 2227**_<br>
**-p** - set listen port; _**./FaNATServer.sh -p 1675**_<br>
**-la** - время для отключения клиентов с низкой активность; _**./FaNATServer.sh -la 60**_<br>
_<h style="font-size:8; ">&emsp;&emsp;&emsp;*если клиент подключён и не используется - он будет отключен от сервера через 60сек.<br>
&emsp;&emsp;&emsp;&ensp;Через 30сек. клиент переподключится к серверу для повторной идентификации в сети.</h>_

## **FaNAT-client**
### Functions  
  - захват, трансляция, просмотр рабочего стола (RTSP, RTMP-поток);
  - оправка, эмуляция сигналов мышки и клавиатуры;
  - отдельно, использование командной строки на управляемом устройстве. Exemple п.9.1 url;
  - возможность запустить ssh-клиент с обратным туннелем и получить доступ к устройству по ssh-протоколу. Exemple п.9.2 url;
  - обмен файлами. Файлы сохраняются в Download folder;
  - консольный вариант для использования в ваших приложениях или как дополнительная служба поддержки при запуске устройства.

### FaNAT-client-fv
**Фул-версия с пользовательским интерфейсом.**<br>
_&ensp;&nbsp;*требуется установка дополнительного ПО_

#### **Available:**
- поиск и управление устройствами в сети;
- захват, трансляция, просмотр рабочего стола;
- отправка сигналов мышки и клавиатуры;
- эмуляцию сигналов мышки и клавиатуры;
- отправка, выполнение инструкций в командной строке на управляемом устройстве и получение результата от него;
- обмен файлами;
- настройка качества видеопотока;
  
#### **Install**
##### &emsp;Windows:
- установите <a href="https://gstreamer.freedesktop.org/features/index.html" target="_blank">GStreamer</a> - url. п.8.1.1;
- загрузите <a href="https://url" target="_blank">архив приложения</a> и разархивируйте его. Запустите **_FaNATClient.ехе_**

##### &emsp;Ubuntu:
- для отображения интерфейса и эмуляции сигналов клавиатуры:
```
#sudo apt-get install '^libxcb.*-dev' libx11-xcb-dev libglu1-mesa-dev libxrender-dev libxi-dev libxkbcommon-dev libxkbcommon-x11-dev -y
```
- дополнительные плагины <a href="https://gstreamer.freedesktop.org/features/index.html" target="_blank">GStreamer</a>:
```
#sudo apt-get install gstreamer1.0-plugins-ugly gstreamer1.0-plugins-bad gstreamer1.0-rtsp -y
```
- загрузите <a href="https://url" target="_blank">архив приложения</a>. В Command Line запустите **_./FaNATClient.sh_**
  
### **FaNAT-client-lite**
**C пользовательским интерфейсом.**<br>
_&ensp;&nbsp;*уменьшен функционал;
_&ensp;&nbsp;*требуется незначительная установка дополнительного ПО_

#### **Available:**
- поиск и управление устройствами в сети;
- просмотр рабочего стола;
- отправка сигналов мышки и клавиатуры;
- отправка, выполнение инструкций в командной строке на управляемом устройстве и получение результата от него;
- обмен файлами;
- настройка качества видеопотока;

#### **Unavailable:**
- захват, трансляцию рабочего стола;
- эмуляция сигналов мышки и клавиатуры;
- в Windows, просмотр RTMP-потока (используйте RTSP-сервер).
  
#### **Install**
##### &emsp;Windows:
- наличие установленного кодека для просмотра видео;
- загрузите <a href="https://url" target="_blank">архив приложения</a> и разархивируйте его. Запустите **_FaNATClient.ехе_**

##### &emsp;Ubuntu:
- для отображения интерфейса и эмуляции сигналов клавиатуры:
```
#sudo apt-get install '^libxcb.*-dev' libx11-xcb-dev libglu1-mesa-dev libxrender-dev libxi-dev libxkbcommon-dev libxkbcommon-x11-dev -y
```
- дополнительные плагины <a href="https://gstreamer.freedesktop.org/features/index.html" target="_blank">GStreamer</a>:
```
#sudo apt-get install gstreamer1.0-libav gstreamer1.0-plugins-bad -y
```
- загрузите <a href="https://url" target="_blank">архив приложения</a>. В Command Line запустите **_./FaNATClient.sh_**

### **FaNAT-client-console-cc**
**Console application. Для использования в ваших приложениях или как дополнительная служба поддержки при запуске устройства.**<br>
_&ensp;&nbsp;*требуется установку дополнительного ПО_

#### **Available:**
- захват, трансляцию рабочего стола;
- эмуляция сигналов мышки и клавиатуры;
- выполнение инструкций в командной строке на управляемом устройстве и отпрвка результатов;
- обмен файлами;
- запуск приложения с дополнительными параметрами;

#### **Unavailable:**
- интерфейс пользователя.
- поиск и управление устройствами в сети;
- отправка сигналов мышки и клавиатуры;
- отображение видеопотока;
  
#### **Install** 
##### &emsp;Windows:
- установите <a href="https://gstreamer.freedesktop.org/features/index.html" target="_blank">GStreamer</a> - url. п.8.1.1;
- загрузите <a href="https://url" target="_blank">архив приложения</a> и разархивируйте его. Запустите **_FaNATClient.ехе_**

##### &emsp;Ubuntu:
- для эмуляции сигналов клавиатуры:
```
#sudo apt-get install '^libxcb.*-dev' libx11-xcb-dev libglu1-mesa-dev libxrender-dev libxi-dev libxkbcommon-dev libxkbcommon-x11-dev -y
```
- дополнительные плагины <a href="https://gstreamer.freedesktop.org/features/index.html" target="_blank">GStreamer</a>:
```
#sudo apt-get install gstreamer1.0-plugins-ugly gstreamer1.0-plugins-bad gstreamer1.0-rtsp -y
```
- загрузите <a href="https://url" target="_blank">архив приложения</a>. В Command Line запустите **_./FaNATClient.sh_**

#### **Start property**
**-spas** - set server password (по умолчанию 1111); _**./FaNATClient.sh -spas 2227**_<br>
**-sip** - set port for connect to server;  _**./FaNATClient.sh -sip 137.34.15.27**_<br>
**-ptcp** - set port for connect to server;  _**./FaNATClient.sh -ptcp 1135**_<br>
**-prtsp** - set port for публикации видео-потока; _**./FaNATClient.sh -prtsp 8554**_<br>
**-prtmp** - set port for публикации видео-потока;  _**./FaNATClient.sh -prtmp 1927**_<br>
**-log** - set ваш логин;  _**./FaNATClient.sh -log user1**_<br>
**-pas** - set ваш пароль;  _**./FaNATClient.sh -pas user1111**_<br>
**-ds** - использовать другой доступный сервер;  _**./FaNATClient.sh -ds 1**_<br>
**-kds** - использовать другой доступный сервер c ключом доступа;  _**./FaNATClient.sh -ds 1 -kds ExxxRt17j**_

### **FaNAT-client-console-cl**
**Console application. Для использования в ваших приложениях или как дополнительная служба поддержки при запуске устройства.**<br>
_&ensp;&nbsp;*уменьшен функционал;_
<br>&ensp;&nbsp;*требуется незначительная установка дополнительного ПО;_

#### **Available:**
- выполнение инструкций в командной строке на управляемом устройстве и отпрвка результатов;
- обмен файлами;
- запуск приложения с дополнительными параметрами;

#### **Unavailable:**
- интерфейс пользователя.
- поиск и управление устройствами в сети;
- отправка сигналов мышки и клавиатуры; 
- эмуляция сигналов мышки и клавиатуры;  
- захват, трансляцию рабочего стола;
- отображение видеопотока;

  
#### **Install** 
##### &emsp;Windows:
- загрузите <a href="https://url" target="_blank">архив приложения</a> и разархивируйте его. Запустите **_FaNATClient.ехе_**

##### &emsp;Ubuntu:
- загрузите <a href="https://url" target="_blank">архив приложения</a>. В Command Line запустите **_./FaNATClient.sh_**

#### **Start property**
**-spas** - set server password (по умолчанию 1111); _**./FaNATClient.sh -spas 2227**_<br>
**-sip** - set port for connect to server;  _**./FaNATClient.sh -sip 137.34.15.27**_<br>
**-ptcp** - set port for connect to server;  _**./FaNATClient.sh -ptcp 1135**_<br>
**-log** - set ваш логин;  _**./FaNATClient.sh -log user1**_<br>
**-pas** - set ваш пароль;  _**./FaNATClient.sh -pas user1111**_<br>
**-ds** - использовать другой доступный сервер;  _**./FaNATClient.sh -ds 1**_<br>
**-kds** - использовать другой доступный сервер c ключом доступа;  _**./FaNATClient.sh -ds 1 -kds ExxxRt17j**_<br>

