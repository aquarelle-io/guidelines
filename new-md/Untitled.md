# [![img](http://makegood.ru/wp-content/uploads/2009/11/logo.gif)](http://makegood.ru/)

Оптимизация и поисковое продвижение сайта, настройка wordpress,
немного юзабилити и самые разные новости в сети...

## [Установка и настройка сервера XAMPP на Windows](http://makegood.ru/tools/xampp/)

19 ноября 2009

![XAMPP for Windows](http://makegood.ru/wp-content/uploads/2009/11/xampp_logo.png)

В этой статье я постараюсь дать наиболее полный обзор веб-сервера XAMPP, сравнение версий для Windows, объясню как его установить, настроить и непосредственно перейти к работе над веб-проектом. В статье рассмотрены следующие темы:

- *Установка веб-сервера XAMPP*
- *Настройка виртуальных хостов*
- *«Отладочная заглушка» для sendmail*
- *Установка WordPress на XAMPP*

Для начала рассмотрим что из себя представляет веб-сервер XAMPP и сравним версии для Windows.

> XAMPP — кроссплатформенная сборка веб-сервера, содержащая Apache, MySQL, интерпретатор скриптов PHP, язык программирования Perl и большое количество дополнительных библиотек, позволяющих запустить полноценный веб-сервер.

На момент написания статьи на сайте доступны для загрузки две версии XAMPP для Windows: XAMPP Windows 1.7.2 [Basic package] и XAMPP Lite 1.7.2.

| Версия веб-сервера                       | **XAMPP Windows 1.7.2 [Basic package]**  | **XAMPP Lite 1.7.2**                     |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| Библиотеки                               | Apache 2.2.12 (IPV6 enabled)             | Apache 2.2.12 (IPV6 enabled)             |
| MySQL 5.1.37 (Community Server) with PBXT engine 1.0.08-rc | MySQL 5.1.37 (Community Server) with PBXT engine 1.0.08-rc |                                          |
| PHP 5.3.0 + PEAR (PEAR, Mail_Mime, MDB2, Zend) | PHP 5.3.0 + PEAR                         |                                          |
| Perl 5.10.0 (Bundle::Apache2, Bundle::Apache::ASP, Bundle::Email, Bundle::DBD::mysql, DBD::SQlite) | Mini Perl 5.10.0                         |                                          |
| XAMPP Control Version 2.5.8 (ApacheFriends Edition) | XAMPP Control Version 2.5.8 (ApacheFriends Edition) |                                          |
| XAMPP CLI Bundle 1.6                     | XAMPP CLI Bundle 1.6                     |                                          |
| XAMPP Port Check 1.4                     | XAMPP Port Check 1.4                     |                                          |
| XAMPP Security 1.1                       | XAMPP Security 1.1                       |                                          |
| SQLite 2.8.17                            | SQLite 2.8.17                            |                                          |
| SQLite 3.6.16                            | SQLite 3.6.16                            |                                          |
| OpenSSL 0.9.8k                           | OpenSSL 0.9.8k                           |                                          |
| phpMyAdmin 3.2.0.1                       | phpMyAdmin 3.2.0.1                       |                                          |
| ADOdb v5.09a                             | *—*                                      |                                          |
| FPDF v1.6                                | *—*                                      |                                          |
| Zend Framework 1.9 Minimal Package (via PEAR) | *—*                                      |                                          |
| Mercury Mail Transport System v4.62      | *—*                                      |                                          |
| msmtp 1.4.17 (a sendmail compatible SMTP client) | msmtp 1.4.17 (a sendmail compatible SMTP client) |                                          |
| FileZilla FTP Server 0.9.32              | *—*                                      |                                          |
| Webalizer 2.21-02 (with GeoIP lite)      | Webalizer 2.21-02 (with GeoIP lite)      |                                          |
| Xdebug 2.0.5 for PHP                     | *—*                                      |                                          |
| eAccelerator 0.9.6-rc1 for PHP           | *—*                                      |                                          |
| Ming 0.4.2 for PHP                       | Ming 0.4.2 for PHP                       |                                          |
| PDF with pdflib lite v7.0.4p4 for PHP    | PDF with pdflib lite v7.0.4p4 for PHP    |                                          |
| Системные требования                     | 128 MB RAM                               | 128 MB RAM                               |
| 256 MB free fixed disk                   | 160 MB free fixed disk                   |                                          |
| Windows 2000, XP (Server 2003), Vista (Server 2008) | Windows 2000, XP (Server 2003), Vista (Server 2008) |                                          |
| all systems 32 bit (64 bit not tested)   | all systems 32 bit (64 bit not tested)   |                                          |
| Размер                                   | EXE 44MB ZIP 84MB                        | EXE 26MB ZIP 56MB                        |
| Станица загрузки                         | [http://www.apachefriends.org/en/xampp-windows.html#641](http://www.apachefriends.org/en/xampp-windows.html#641) | [http://www.apachefriends.org/en/xampp-windows.html#646](http://www.apachefriends.org/en/xampp-windows.html#646) |

Вопрос выбора версии заключается лишь в наличии необходимых библиотек (см. табл. выше), облегченная версия по заявлению авторов обновляется не так часто как полный пакет, процесс установки обеих версий абсолютно идентичен. Переходим на сайт по указанным выше ссылкам и качаем подходящую вам версию (в обзоре я буду говорить об установке и настройке XAMPP Windows 1.7.2 [Basic package], установка производилась на Windows 7 Ultimate x86).

## Установка веб-сервера XAMPP

*1. Начинаем установку XAMPP. Откроется окно, в котором нам предлагается выбрать путь для размещения сервера. По-умолчанию это диск C:\. Я не буду изменять путь и установлю сервер на предложенный диск. Нажимаем кнопку Install и ждем пока дистрибутив полностью распакуется.*

- ![img_01](http://makegood.ru/wp-content/uploads/2009/11/img_01.jpg)


- ![img_02](http://makegood.ru/wp-content/uploads/2009/11/img_02.jpg)

*2. После распаковки дистрибутива запустится командная строка, далее основная установка будет происходить через нее. XAMPP предлагает создать ярлыки на рабочем столе и в меню пуск, нажимаем enter.*

- ![img_03](http://makegood.ru/wp-content/uploads/2009/11/img_03.jpg)

*3. Теперь у нас спрашивают, правильно ли выбран каталог установки XAMPP, по-умолчанию сервер будет располагаться по следующему адресу C:\xampp, нажимаем enter.*

- ![img_04](http://makegood.ru/wp-content/uploads/2009/11/img_04.jpg)

*4. Хотим ли мы установить портативную версию? Нажимаем enter, т.к. XAMPP устанавливается на жесткий диск.*

- ![img_05](http://makegood.ru/wp-content/uploads/2009/11/img_05.jpg)

*5. Окончательная установка XAMPP. Нажимаем enter для продолжения.*

- ![img_06](http://makegood.ru/wp-content/uploads/2009/11/img_06.jpg)

*6. Автоматический выбор часового пояса. Нажимаем enter.*

- ![img_07](http://makegood.ru/wp-content/uploads/2009/11/img_07.jpg)

*7. Запустим панель управления XAMPP (XAMPP Control Panel), выбираем 1 и жмем enter.*

- ![img_09](http://makegood.ru/wp-content/uploads/2009/11/img_09.jpg)

*8. Открылась панель управления сервером. Закрываем командную строку.*

- ![img_10](http://makegood.ru/wp-content/uploads/2009/11/img_10.jpg)

Подсказки по панели управления:

*Checkboxes (Svc)* - устанавливает модуль в качестве службы Windows (если вы хотите запускать какой либо модуль (Apache, MySQL и т.д.) как службу, то отмечаем соответствующие флажки)

*Admin* - запускует администрирование модулем (Admin напротив модуля Apache - откроет окно приветствия XAMPP, выбираем язык. И попадаем в веб-интерфейс XAMPP, здесь можно проверить демонстрационные примеры в разделе Demos, узнать информацию о модулях и т.д. Admin напротив модуля MySQL - запустит phpMyAdmin)

*Shell* - запуск командной строки для работы с сервером;

*Setup* - открывает командную строку для настройки XAMPP;

*Port-Check* - проверка портов;

*Explore* - открывает папку в которую установлен XAMPP, в нашем случае C:\xampp;

*SCM* - открывает окно управления службами Windows;

*Refresh* - обновление состояния модулей;

Запускается XAMPP с помощью ярлыка на рабочем столе или в меню пуск, если же вы при установке отказались от создания ярлыков, вы можете запустить XAMPP с помощью файла xampp-control.exe в директории C:\xampp, там же вы можете увидеть все остальные ярлыки, которыми можно запустить отдельные модули, деинсталировать XAMPP и т.п.

Иконка XAMPP удобно сидит в трее и при щелчке левой кнопки мыши открывает панель управления (XAMPP Control Panel).

*9. Запускаем модули Apache и MySQL (кнопки Start), набираем в браузере localhost (или жмем Admin напротив модуля Apache):*

- ![img_11](http://makegood.ru/wp-content/uploads/2009/11/img_11.jpg)

*10. П**ри первом запуске откроется страница приветствия, выбираем один из предложенных языков:*

- ![img_12](http://makegood.ru/wp-content/uploads/2009/11/img_12.jpg)

*11. **Попадаем в веб-интерфейс XAMPP, здесь вы можете ознакомиться документацией, примерами в разделе Demos и т.д.:*

- ![img_13](http://makegood.ru/wp-content/uploads/2009/11/img_13.jpg)

В разделе Security находятся настройки безопасности:

- ![img_14](http://makegood.ru/wp-content/uploads/2009/11/img_14.jpg)

Перейдя по указанной ссылке *http://localhost/security/xamppsecurity.php*, можно задать пароль для администратора баз данных MySQL и можно установить пароль на директорию XAMPP для ограничения доступа из локальной сети:

- ![img_15](http://makegood.ru/wp-content/uploads/2009/11/img_15.jpg)

Итак, мы установили и ознакомились с веб-сервером XAMPP, теперь настало время создать тестовую страницу и разместить наш проект.

Для того чтобы создать новый сайт на локальном веб-сервере, необходимо создать папку с названием сайта в папке C:\xampp\htdocs\, например blog и создадим там тестовый php-скрипт с кодом:

```
<?php
echo 'Hello world!';
?>
```

Сохраним как index.php. Структура папок:

Переходим в браузере по адресу http://localhost/blog/ и, если все сделано правильно, видим приветствие "Hello world!", тем самым мы протестировали работоспособность сервера:

- ![img_16](http://makegood.ru/wp-content/uploads/2009/11/img_16.jpg)

> Веб-сервер можно установить и другим способом, для этого необходимо распаковать инсталятор или ZIP-архив в любое удобное для вас место на жестком диске, название папки xampp можно переименовать, например в server и запустить установку с помощью файла setup_xampp.bat в этой папке, повторить все шаги описанные выше.
>
> Если вы устанавливаете XAMPP впервые, то рекомендую на время первого ознакомления не менять названия папок и установить веб-сервер по дефолту, чтобы потом не искать ошибок, которые могут возникнуть при указании неверных путей для виртуальных хостов, речь о которых пойдет ниже.

## Настройка виртуальных хостов

Если мы хотим хранить свои проекты в другой папке (например, Мои документы) или локальная версия сайта должна работать при переходе по адресу www.blog.ru вам необходимо разобраться с настройкой виртуальных хостов, об этом и пойдет речь в данном подразделе.

Предположим наш сайт должен храниться на диске C в папке my_projects (C:\my_projects), в браузере он должен открываться по адресу www.blog.local или blog.local.

Создадим в папке my_projects папку с названием blog.local, в ней создадим папки www и logs. В папку www положим наш тестовый скрипт index.php.

Вот так это будет выглядеть в файловой системе Windows:

- ![folders](http://makegood.ru/wp-content/uploads/2009/11/folders.png)

Теперь перейдем к настройке виртуальных хостов. Открываем в текстовом редакторе файл httpd-vhosts.conf, расположенный по следующему адресу: C:\xampp\apache\conf\extra.

> Примечание: рекомендую для большего удобства создать сразу ярлык для этого файла, например в папке C:\xampp, чтобы потом можно было быстро добавлять новые виртуальные хосты.

Все что находится в файле httpd-vhosts.conf мы трогать не будем, а просто добавим наши хосты (просто скопируйте и вставьте в файл приведенный ниже код):

```
NameVirtualHost *:80

<VirtualHost *:80>
    DocumentRoot "C:\xampp\htdocs"
    ServerName localhost
</VirtualHost>

<VirtualHost *:80>
    ServerAdmin webmaster@blog.local
    DocumentRoot "C:\my_projects\blog.local\www"
    ServerName blog.local
    ServerAlias www.blog.local
    ErrorLog "C:\my_projects\blog.local\logs\error.log"
    CustomLog "C:\my_projects\blog.local\logs\access.log" combined
  <Directory "C:\my_projects\blog.local\www">
    AllowOverride All
    Order allow,deny
    Allow from all
  </Directory>
</VirtualHost>
```

Верхний виртуальный хост, выделен другим цветом, позволит нам по прежнему заходить на localhost (локальный сайт XAMPP).

Следующим шагом нам потребуется добавить две строчки в файл hosts, расположенный по следующему адресу C:\Windows\System32\drivers\etc\hosts (также рекомендую создать для него ярлык в папке сервера):

```
127.0.0.1     blog.local
127.0.0.1     www.blog.local
```

Заходим в панель управления XAMPP (XAMPP Control Panel) и перезапускаем Apache. Теперь проверим наш сайт, который должен работать по адресу www.blog.local. Если все сделано верно, то мы увидим приветствие "Hello world!".

Так как скорее всего понадобится создание нескольких сайтов на локальном сервере, приведу пример добавления хостов в файл httpd-vhosts.conf. Предположим новый сайт будет называться site.local:

```
NameVirtualHost *:80

<VirtualHost *:80>
    DocumentRoot "C:\xampp\htdocs"
    ServerName localhost
</VirtualHost>

<VirtualHost *:80>
    ServerAdmin webmaster@blog.local
    DocumentRoot "C:\my_projects\blog.local\www"
    ServerName blog.local
    ServerAlias www.blog.local
    ErrorLog "C:\my_projects\blog.local\logs\error.log"
    CustomLog "C:\my_projects\blog.local\logs\access.log" combined
  <Directory "C:\my_projects\blog.local\www">
    AllowOverride All
    Order allow,deny
    Allow from all
  </Directory>
</VirtualHost>

<VirtualHost *:80>
    ServerAdmin webmaster@site.local
    DocumentRoot "C:\my_projects\site.local\www"
    ServerName site.local
    ServerAlias www.site.local
    ErrorLog "C:\my_projects\site.local\logs\error.log"
    CustomLog "C:\my_projects\site.local\logs\access.log" combined
  <Directory "C:\my_projects\site.local\www">
    AllowOverride All
    Order allow,deny
    Allow from all
  </Directory>
</VirtualHost>
```

Также не забываем добавить следующие строчки в файл hosts в папке Windows:

```
127.0.0.1     site.local
127.0.0.1     www.site.local
```

Перезапускаем Apache и новый хост готов для работы.

По аналогии можно добавить сколько угодно виртуальных хостов.

Немного справочной информации относительно того, что мы добавляем в файл httpd-vhosts.conf:

`ServerAdmin webmaster@blog.local` - e-mail-адрес администратора веб-сервера;

`DocumentRoot "C:\my_projects\blog.local\www"` - путь к папке с сайтом;

`ServerName blog.local` - название сайта, которое набирается в браузере, может иметь любое значение, например blog или blog.ru;

`ServerAlias www.blog.local` - адрес по которому сайт также должен открываться;

`ErrorLog "C:\my_projects\blog.local\logs\error.log"` - журнал ошибок;

`CustomLog "C:\my_projects\blog.local\logs\access.log" combined` - журнал доступа к сайту, кто и когда заходил на сайт и с какого браузера, combined - означает, что отчет будет более информативным, можно заменить значением common (менее информативно);

```
<Directory "C:\my_projects\blog.local\www">
  AllowOverride All
  Order allow,deny
  Allow from all
</Directory>
```

Приведенная выше конструкция разрешает отображение всех файлов в указанной директории и назначает максимально возможные привилегии (без `AllowOverride All` не будут работать ЧПУ).

Если делали все внимательно, то создание новых сайтов на виртуальном сервере не составит для вас труда, ошибки могут быть из-за синтаксиса, к примеру если вы допустите ошибку в httpd-vhosts.conf, Apache может просто не запустится. Для анализа ошибок воспользйтесь логами Apache, файл error.txt расположенный в по адресу C:\xampp\apache\logs.

## «Отладочная заглушка» для sendmail

Если вы пользовались Denwer-ом, то помните, что все письма с локального сайта отправлялись в папку sendmail, это достаточно удобно, но в XAMPP такой функции не предусмотрено, в XAMPP есть собственный почтовый сервер, но он потребует немало времени, чтобы с ним разобраться.

С помощью описанной ниже инструкции, вы сможете создать такую же "заглушку" как и в Denwer.

*1. В папке sendmail (C:\xampp\sendmail) создадим файл sendmail.php с кодом:*

```
<?php

define('DIR','c:/xampp/tmp/sendmail/');

$stream = '';
$fp = fopen('php://stdin','r');
while($t=fread($fp,2048))
{
if( $t===chr(0) )
break;
$stream .= $t;
}
fclose($fp);

$fp = fopen(mkname(),'w');
fwrite($fp,$stream);
fclose($fp);

function mkname($i=0)
{
$fn = DIR.date('Y-m-d_H-i-s_').$i.'.eml';
if ( file_exists($fn) )
return mkname(++$i);
else return $fn;
}

?>
```

*В моем случае предполагается получение писем в кодировке UTF-8, если вы хотите получать письма в в кодировке CP1251, то замените строчку:*

`fwrite($fp,$stream);`

*на строчку:*

`fwrite($fp,iconv("UTF-8","CP1251",$stream));`

*2. В файле php.ini (C:\xampp\php) заменяем строчку:*

`sendmail_path = "C:\xampp\sendmail\sendmail.exe -t"`

*на строчку:*

`sendmail_path = C:\xampp\php\php.exe c:\xampp\sendmail\sendmail.php`

*Строка должна быть раскомментирована (убрать символ точки с запятой ";" в начале строки).*

*3. Создадим папку sendmail в папке tmp (C:\xampp\tmp\sendmail).*

*4. Перезапускаем сервер Apache и теперь все отправленные письма будут в папке C:\xampp\tmp\sendmail*

*Руководство по созданию "отладочной заглушки" для XAMPP было предложено Anton L. Safin.*

## Установка WordPress на XAMPP

Для установки WordPress будем использовать, ранее созданный, виртуальный хост blog.local, следовательно и файлы движка будут располагаться в папке blog.local (C:\my_projects\blog.local\www).

*1. Скачиваем свежую версию WordPress с официального сайта www.wordpress.org и распаковываем архив в папку www (содержимое папки wordpress в архиве).*

*2. Перейдем в phpMyAdmin и создадим базу данных для нашего блога:*

- ![img_17](http://makegood.ru/wp-content/uploads/2009/11/img_17.jpg)

*Новая база данных: blog; сравнение: utf8_general_ci; сопоставление соединения с MySQL: utf8_general_ci → нажимаем кнопку Создать.*

*Итак, база данных создана:*

- ![img_18](http://makegood.ru/wp-content/uploads/2009/11/img_18.jpg)

*3. Вернемся в папку в которую мы распаковали WordPress и найдем файл wp-config-sample.php, переименуем его в wp-config.php и откроем в любом текстовом редакторе, который поддерживает кодировку UTF-8 и введем свои данные:*

*- Имя базы данных для WordPress: blog;*

*- Имя пользователя MySQL: root;*

*- Пароль пользователя MySQL: оставляем пустым, если в настройках Security ничего не указывали;*

*- Адрес сервера MySQL: localhost;*

*- Кодировка базы данных при создании таблиц: utf8;*

*- Схема сопоставления: utf8_general_ci;*

*Выглядеть это должно так:*

```
/** Имя базы данных для WordPress */
define('DB_NAME', 'blog');

/** Имя пользователя MySQL */
define('DB_USER', 'root');

/** Пароль пользователя MySQL */
define('DB_PASSWORD', '');

/** Адрес сервера MySQL */
define('DB_HOST', 'localhost');

/** Кодировка базы данных при создании таблиц. */
define('DB_CHARSET', 'utf8');

/** Схема сопоставления. Не меняйте, если не уверены. */
define('DB_COLLATE', 'utf8_general_ci');
```

*Сохраняем и закрываем файл.*

*Важно чтобы все изменения в файле wp-config.php сохранились в кодировке UTF-8!*

*4. Переходим в браузере по адресу **blog.local и видим страницу приветствия WordPress, вводим название блога и e-mail администратора (все письма мы можем посмотреть в папке sendmail, речь о которой шла выше):*

- ![img_19](http://makegood.ru/wp-content/uploads/2009/11/img_19.jpg)

*Нажимаем "Установить WordPress" и попадаем на страницу с логином и паролем:*

- ![img_20](http://makegood.ru/wp-content/uploads/2009/11/img_20.jpg)

*Вход в панель администрирования блогом: **http://blog.local/wp-admin/*

- ![img_21](http://makegood.ru/wp-content/uploads/2009/11/img_21.jpg)

*Переход на блог: http://**blog.local*

- ![img_22](http://makegood.ru/wp-content/uploads/2009/11/img_22.jpg)

> *Установку WordPress можно произвести и альтернативным способом, для этого после распаковки архива с движком и создания базы данных, наберите в адресной строке браузера название вашего блога, WordPress предложит создать файл wp-config.php через веб-интерфейс.*

*Рекомендую для прочтения статью: Домены с www и без на wordpress*

В заключении хочу сказать, что XAMPP очень понравился в работе, работает быстро, ошибок нет, то, что некоторые надстройки надо выполнять вручную, я считаю только плюсом.