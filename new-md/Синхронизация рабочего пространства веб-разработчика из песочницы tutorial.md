1 октября 2013 в 13:04

# Синхронизация рабочего пространства веб-разработчика [из песочницы](https://habrahabr.ru/sandbox/) tutorial

[Разработка веб-сайтов](https://habrahabr.ru/hub/webdev/)*

- Синхронизация рабочих файлов сайтов ( PHP, HTML, CSS, etc ) таким образом, чтобы они могли редактироваться на обоих системах ( Windows, Mac )
- Синхронизация баз данных
- Синхронизация настроек IDE, плагинов и сниппетов
- Возможность локальной работы, без интернета. Поэтому были исключены многие онлайн сервисы, такие как [koding.com](http://koding.com/).
- Возможность синхронизации через используемый мной облачный диск Google Drive

 

 

**AMPPS**

- Кроссплатформенный( Windows, Mac OSX )
- Бесплатный
- Удобный интерфейс запуска и настройки сервера
- Полная синхронность версий PHP, MySQL и других. Обновление в один клик
- Отличный web-интерфейс, с кучей возможностей. Например, установка любой CMS или фреймворка.
- Поддержка MongoDB ( мне он не нужен, но вдруг кому-то необходим )

 

 

 

 

```
# DocumentRoot: The directory out of which you will serve your
# documents. By default, all requests are taken from this directory, but
# symbolic links and aliases may be used to point to other locations.
#
DocumentRoot "D:\путь\к вашему\облачному диску"

```

```
# Replication Master Server (default)
# binary logging is required for replication
#log-bin=mysql-bin

```

Для первой машины, Windows:

```
cd “C:\путь\к\AMPPS\mysql”
mkdir "D:\путь\к\облачному\диску\mysql"
mv data “D:\путь\к\облачному диску\Sublime\User”
cmd /c mklink /D data "D:\путь\к\облачному\диску\mysql\data"

```

Для каждой последующей, Windows:

```
cd "C:\путь\к\AMPPS\mysql\"
rmdir -recurse data
cmd /c mklink /D data "D:\путь\к\облачному\диску\mysql\data\"

```

Для первой машины, MacOSX:

```
cd ~/Application/AMPPS/mysql/
mkdir ~/путь/к папке/облачного диска/mysql/
mv data ~/путь/к папке/облачного диска/mysql/
ln -s /путь/к папке/облачного диска data

```

Для каждой последующей машины, MacOSX:

```
cd ~/Application/AMPPS/mysql/
rm -r data
ln -s /путь/к папке/облачного диска data

```

 

localhost/ampps

 

 

Для первой машины, Windows:

```
cd "$env:appdata\Sublime Text 3\Packages\"
mkdir “D:\путь\к\облачному диску\Sublime”
mv User “D:\путь\к\облачному диску\Sublime\User”
cmd /c mklink /D User “D:\путь\к\облачному диску\Sublime\User”

```

Для каждой последующей, машины Windows:

```
cd "$env:appdata\Sublime Text 3\Packages\"
rmdir -recurse User
cmd /c mklink /D User “D:\путь\к\облачному диску\Sublime\User”

```

Для первой машины, MacOSX:

 

```
cd ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/
mkdir ~/путь/к папке/облачного диска/Sublime
mv User ~/путь/к папке/облачного диска/Sublime
ln -s ~/путь/к папке/облачного диска/Sublime/User

```

Для каждой последующей машины, MacOSX:

 

```
cd ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/
rm -r User
ln -s ~/путь/к папке/облачного диска/Sublime/User

```

 

-  

- [синхронизация](https://habrahabr.ru/search/?q=%5B%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F%5D&target_type=posts), 

- [рабочее пространство](https://habrahabr.ru/search/?q=%5B%D1%80%D0%B0%D0%B1%D0%BE%D1%87%D0%B5%D0%B5%20%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D1%81%D1%82%D0%B2%D0%BE%5D&target_type=posts), 

- [облачный диск](https://habrahabr.ru/search/?q=%5B%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B9%20%D0%B4%D0%B8%D1%81%D0%BA%5D&target_type=posts), 

- [web-разработка](https://habrahabr.ru/search/?q=%5Bweb-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B0%5D&target_type=posts), 

- [dropbox](https://habrahabr.ru/search/?q=%5Bdropbox%5D&target_type=posts), 

- [google drive](https://habrahabr.ru/search/?q=%5Bgoogle%20drive%5D&target_type=posts), 

- [yandex disk](https://habrahabr.ru/search/?q=%5Byandex%20disk%5D&target_type=posts), 

- [sublime text](https://habrahabr.ru/search/?q=%5Bsublime%20text%5D&target_type=posts)