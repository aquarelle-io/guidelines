# Настройка среды разработки PHP в Windows

В данном учебном курсе рассматриваются два способа настройки среды разработки PHP в операционной системе Windows. Первый и наиболее удобный способ состоит в установке и настройке пакета AMP (**A**pache, **М**ySQL, **P**HP). В данном учебном курсе приводится процедура установки пакета XAMPP. Второй способ состоит в установке и настройке каждого компонента по отдельности.

**Содержание**

- Использование пакета AMP
  - [Установка и настройка пакета XAMPP](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#installConfigureXAMPP)
  - [Проверка установки XAMPP](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#checkXAMPPInstallation)
  - [Установка и включение отладчика XDebug](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#installAndEnableXDebug)
- Установка компонентов по отдельности
  - [Сервер HTTP Apache](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#installApacheComponent)
  - [Механизм PHP](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#installPHPEngine)
  - [Сервер базы данных MySQL](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#installMySQL)
  - [XDebug](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#installXDebug)
  - [Настройка среды](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#settingUpEnvironment)

**Для работы с этим учебным курсом требуется следующее программное обеспечение и ресурсы.**

| Программное обеспечение или материал     | Требуемая версия                         |
| ---------------------------------------- | ---------------------------------------- |
| [IDE NetBeans](https://netbeans.org/downloads/index.html) | Пакет загрузки PHP                       |
| Механизм PHP                             | Версия 5. Содержится в [XAMPP Windows](http://www.apachefriends.org/en/xampp-windows.html). |
| Веб-сервер                               | Рекомендуется использовать [сервер HTTP Apache версии 2.2](http://httpd.apache.org/download.cgi).Содержится в XAMPP для Windows. |
| Сервер базы данных                       | Рекомендуется использовать [сервер MySQL 5.0](http://dev.mysql.com/downloads/mysql/5.1.html).Содержится в XAMPP для Windows. |
| Отладчик PHP (не обязательно)            | [Версия XDebug 2.0 или выше.](http://www.xdebug.org/) |

Как правило, разработка и отладка выполняются на локальном веб-сервере, в то время как производственная среда размещена на удаленном веб-сервере. Настройка удаленного веб-сервера описана в разделе[Развертывание приложения PHP на удаленном веб-сервере с помощью IDE NetBeans](https://netbeans.org/kb/docs/php/remote-hosting-and-ftp-account.html). Этот учебный курс содержит информацию, необходимую для настройки локального веб-сервера. Поддержка PHP может добавляться к целому ряду локальных веб-серверов (IIS, Xitami и т.д.), но обычно используется [сервер HTTP Apache](http://httpd.apache.org/download.cgi). Сервер HTTP Apache включен в пакет AMP XAMPP, используемый в этом учебном курсе. Сведения относительно установки и настройки автономного сервера HTTP Apache приведены [здесь](http://httpd.apache.org/docs/2.2/install.html).

## Требуемое программное обеспечение

Для создания, выполнения и отладки проектов PHP необходимо следующее программное обеспечение:

- IDE NetBeans для PHP. Загрузку можно осуществить [отсюда](https://netbeans.org/downloads/index.html).
- Веб-сервер. Как правило, разработка и отладка выполняются на локальном веб-сервере, в то время как производственная среда размещена на удаленном веб-сервере. Текущая версия позволяет использовать локальный сервер. Последующие версии будут поддерживать использование удаленного сервера с доступом по протоколу FTP. Поддержка PHP может добавляться к целому ряду веб-серверов (IIS, Xitami и т.д.), но обычно используется [сервер HTTP Apache](http://httpd.apache.org/download.cgi). Сведения относительно установки и настройки Apache 2.2 приведены [здесь](http://httpd.apache.org/docs/2.2/install.html).


- Механизм PHP. Поддерживается версия PHP5. Загрузку можно осуществить [отсюда](http://www.php.net/downloads.php).
- Отладчик PHP. IDE NetBeans для PHP позволяет использовать [XDebug](http://www.xdebug.org/), но использование отладчика не является обзательным. Из соображений совместимости с PHP5 рекомендуется использовать версию XDebug 2.0 или выше.
- Сервер базы данных. Существует возможность использования различных серверов базы данных, однако самым популярным из них является сервер MySQL. Загрузку можно осуществить [отсюда](http://dev.mysql.com/downloads/mysql/5.1.html). 
  **Примечание.** Рекомендуемая версия продукта: MySQL Server 5.0. В предоставленных документах описывается работа с этой версией.

По завершении установки необходимо выполнить настройку среды в целях обеспечения правильной совместной работы всех программных компонентов.

Можно использовать [пакет](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#XAMPP), содержащий требуемое программное обеспечение, или [установить каждый компонент по отдельности](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#installComponentsSeparately).

## Использование пакета AMP

В целях автоматической установки всех параметров настройки для механизма PHP, сервера HTTP Apache и сервера базы данных MySQL воспользуйтесь пакетом AMP. В данном учебном курсе приведены указания только для пакета [XAMPP-Windows](http://www.apachefriends.org/en/xampp-windows.html). Справочные сведения по пакету WAMP или другим пакетам приведены в разделе [NetBeans XDebug Wiki](http://wiki.netbeans.org/HowToConfigureXDebug).

### Установка и настройка пакета XAMPP

В этом разделе приведено описание процедур загрузки, установки и настройки пакета XAMPP.

**Предупреждение!** НЕ используйте XAMPP 1.7.0. В этой версии имеются значительные проблемы с XDebug. Используйте версию 1.7.1 или выше, где эти неполадки устранены.

**Примечание: **Начиная с XAMPP 1.7.2, XAMPP поставляется с PHP 5.3а не с PHP 5.2.x. IDE NetBeans для PHP версии 6.7.x не поддерживает новые функции PHP 5.3. IDE NetBeans для PHP 6.8, которая в настоящее время доступна как сборка разработки, полностью поддерживает PHP 5.3. Также обратите внимание, что установка Xdebug различается для PHP 5.2.x и PHP 5.3.

1. Загрузите пакет программы установки [XAMPP ](http://www.apachefriends.org/en/xampp-windows.html). В состав XAMPP Lite не входит XDebug.

2. По завершении загрузки запустите файл

    

   EXE

   .

   В Microsoft Vista функция контроля учетных записей пользователей (UAC) блокирует обновление установщиком PHP настройки службы httpd Apache. На время установки XAMPP следует отключить UAC. Для получения дополнительных сведений обратитесь к разделу [Поддержка Майкрософт](http://support.microsoft.com/kb/922708).

3. Можно установить сервер Apache и сервер базы данных MySQL как веб-службы. Если Apache Server и MySQL установлены как службы, то нет необходимости запускать их вручную с помощью "XAMP Control Panel". Следует учитывать, что установить и удалить эти службы можно с помощью [панели управления XAMPP](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#xamppConstolPanel).

4. При использовании самораспаковывающегося архива после его распаковки запустите файл `setup-xampp.bat` для настройки компонентов пакета. Программа установки XAMPP запускает этот файл автоматически.

5. ​

   После настройки откройте панель управления XAMP. Эту панель можно открыть посредством запуска файла

    

   XAMPP_HOME/xampp-control.exe

    

   или с помощью значка панель управления XAMPP, автоматически размещаемого на рабочем столе. При открытии панели управления XAMPP следует учитывать, что модули, установленные как службы, уже выполняются.

   **Предупреждение. **Иногда в Windows Vista не удается запустить файл `xampp-control.exe`. В этом случае можно запустить `xampp-start.exe`.

   **Предупреждение. **Файл `winmysqladmin.exe`, запускаемый кнопкой "Admin" для MySQL, не функционирует. Отображается последовательность сообщений об ошибках, которая может быть остановлена только путем завершения процесса `winmysqladmin` вручную. Файл `winmysqladmin.exe` также невозможно запустить из командной строки. Обратитесь к странице [http://bugs.xampp.org/view.php?id=71](http://bugs.xampp.org/view.php?id=71).

   ​

6. Флажки "Svc" указывают на то, что модуль устанавливается как служба Windows и автоматически выполняется при запуске системы. Службы Windows устанавливаются и удаляются при установке и снятии флажка "Svc". При удалении службы Windows сам модуль не удаляется, однако необходимо запускать его вручную. Панель управления XAMPP включает в себя кнопки запуска и остановки модулей, а также открытия их консолей администратора.

### Проверка установки XAMPP

1. Запустите браузер и введите следующий URL-адрес: `http://localhost`. Откроется страница приветствия XAMPP:
   ![Страница приветствия XAMPP, указывающая, что Apache запущен](https://netbeans.org/images_www/articles/72/php/configure-php-environment-windows/xampp-welcome-page.png)
2. В целях обеспечения установки серверов Apache и MySQL в качестве служб системы перезапустите операционную систему, запустите браузер и повторно введите URL-адрес `http://localhost`. Откроется страница приветствия XAMPP. Обратите внимание на то, что в левом поле страницы приветствия XAMPP имеется меню, посредством которого можно проверить состояние компонентов XAMPP, запустить `phpinfo()`, а также воспользоваться другими важными функциями. При выполнении `phpinfo()` возвращается экран с информацией о настройке компонентов XAMPP. 
   ![Таблица сведений конфигурации, возвращенная phpinfo()](https://netbeans.org/images_www/articles/72/php/configure-php-environment-windows/xampp-phpinfo.png)

### Установка и включение отладчика XDebug

Для использования отладчика XDebug необходимо настроить стек PHP. Процесс отличается, если используется [XAMPP 1.7.1](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#xdebug-xampp-171), который включает в себя PHP 5.2.6, или [XAMPP 1.7.2](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#xdebug-xampp-172), который включает в себя PHP 5.3.

Многие пользователи испытывают трудности при настройке работы XDebug в своих системах. Справочные сведения приведены на [вики-странице](http://wiki.netbeans.org/HowToConfigureXDebug)и [на форуме пользователей редактора NetBeans PHP Editor](http://forums.netbeans.org/viewforum.php?f=13&sid=5b63e6774fe7859b5edd35b1192d8efd).

#### XDebug на XAMPP 1.7.1 (PHP 5.2)

Необходимо скачать XDebug, поместить файл .dll в базовый каталог php и настроить php.ini для поиска и использования данного файла.

1. Загрузите самую последнюю, *ориентированную на многопотоковое исполнение* версию [XDebug](http://www.xdebug.org/download.php), совместимую с вашей версией PHP. Ссылки для загрузки перечислены в разделе "Releases". Скопируйте файл `.dll` в каталог `XAMP_HOME/php/ext`. (`XAMPP_HOME` ссылается на каталог установки XAMPP или XAMPP Lite, например, `C:\Program Files\xampp` или `C:\xampplite`.)

2. Найдите и откройте активный файл `php.ini` для XAMPP. По умолчанию он находится в каталоге `XAMPP_HOME/apache/bin`. Подтвердите, какой файл `php.ini` является активным, с помощью `phpinfo()` и поиска загруженного файла конфигурации.

3. Поскольку оптимизатор Zend блокирует XDebug, оптимизатор требуется отключить. В активном файле

    

   php.ini 

   найдите следующие строки и удалите или отметьте их как комментарии (для надежности выполните поиск и закомментируйте все свойства, связанные с Zend):

   ```
   [Zend]
   ;zend_extension_ts = "C:\Program Files\xampp\php\zendOptimizer\lib\ZendExtensionManager.dll"
   ;zend_extension_manager.optimizer_ts = "C:\Program Files\xampplite\php\zendOptimizer\lib\Optimizer"
   ;zend_optimizer.enable_loader = 0
   ;zend_optimizer.optimization_level=15
   ;zend_optimizer.license_path =

   ```

4. Для присоединения

   ​

    

   XDebug к механизму PHP раскомментируйте следующие строки в файлах

    

   php.ini

    

   (добавьте эти строки непосредственно в разделе [Zend]), если они отсутствуют. Добавлены дополнительные примечания.

   ```
   [XDebug]
   ; Only Zend OR (!) XDebug
   zend_extension_ts = "./php/ext/php_xdebug<-version-number>.dll"
   ; XAMPP and XAMPP Lite 1.7.0 and later come with a bundled xdebug at <XAMPP_HOME>/php/ext/php_xdebug.dll, without a version number.
   xdebug.remote_enable=1
   xdebug.remote_host=127.0.0.1
   xdebug.remote_port=9000
   ; Port number must match debugger port number in NetBeans IDE Tools > Options > PHP
   xdebug.remote_handler=dbgp
   xdebug.profiler_enable=1
   xdebug.profiler_output_dir="<XAMPP_HOME>\tmp"

     
   ```

   Установите свойство `xdebug.remote_enable` в значение 1, а не в значение "true" или другое значение.

   **Примечание.** Убедитесь в том, что указанные пути соответствуют расположению соответствующих файлов, как это определено при установке.

5. Сохраните файл `php.ini`.

6. Запустите [панель управления XAMPP](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#xamppConstolPanel) и перезапустите сервер Apache.

 

вики-странице

 

 

документации по XDebug

#### Xdebug на XAMPP 1.7.2 (PHP 5.3)

XAMPP 1.7.2 поставляется вместе с соответствующим файлом Xdebug .dll. Для начала использования необходимо только настроить `php.ini`. Обратите внимание, что все настройки Xdebug сопровождаются поясняющим текстом.

1. Найдите и откройте файл `XAMPP_HOME\php\php.ini` для редактирования. В XAMPP 1.7.2 используется только файл `php.ini`
2. Найдите строку `zend_extension = "XAMPP_HOME\php\ext\php_xdebug.dll"` и удалите символ комментария.
3. Найдите строку `xdebug.remote_host=localhost` и удалите символ комментария. Измените значение параметра `localhost` на `127.0.0.1`.
4. Найдите строку `xdebug.remote_enable = 0` и удалите символ комментария. Измените 0 на 1.
5. Найдите строку `xdebug.remote_handler = "dbgp"` и удалите символ комментария.
6. Найдите строку `xdebug.remote_port = 9000` и удалите символ комментария.
7. Сохраните файл `php.ini`.
8. Запустите [панель управления XAMPP](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#xamppConstolPanel) и перезапустите сервер Apache.

Дополнительные сведения о настройке XDebug приведены на [вики-странице](http://wiki.netbeans.org/HowToConfigureXDebug) и в [документации по XDebug](http://www.xdebug.org/docs/install).

## Установка компонентов по отдельности

### Сервер HTTP Apache

1. Загрузите [сервер HTTP Apache2](http://httpd.apache.org/download.cgi).

2. Запустите установочный файл

    

   .msi

   . Запускается мастер установки. Следуйте указаниям.

   В Microsoft Vista не следует устанавливать Apache Server в местоположение по умолчанию, находящееся в папке "Program Files". Все файлы в папке "Program Files" защищены от записи.

3. По завершении установки перезапустите сервер Apache.

4. Для проверки успешности установки запустите браузер и введите следующий URL-адрес:

   ```
     http://localhost/
   ```

   Откроется страница приветствия Apache:

    

   ​

   ​

#### Устранение проблем

1. Откройте файл настройки веб-сервера Apache `httpd.conf`. По умолчанию файл расположен в `C:\Program Files\Apache Software Foundation\Apache<version>\conf\`.
2. Перейдите к строке `Listen 80` и замените номер порта: например, на `8080`. Сохраните файл.
3. Перезапустите веб-сервер Apache.
4. Для проверки работоспособности веб-сервера запустите браузер, введите URL-адрес и явно укажите номер порта: `http://localhost:8080`

Кроме того, можно также приостановить процессы, прослушивающие порт 80. В окне "Диспетчер задач" выберите соответствующее имя файла и нажмите кнопку "Завершить процесс".

Дополнительные сведения об установке и настройке сервера приведены [здесь](http://httpd.apache.org/docs/2.2/install.html).

### Механизм PHP

1. Загрузите

    

   бинарный пакет установщика Windows

    

   для выбранной версии PHP5.

   **Важно.**Если установщик для нужной версии PHP отсутствует, установите ее вручную из файла .zip. См. раздел [Этапы ручной установки](http://php.net/manual/en/install.windows.manual.php) в документации php.net.

2. По завершении загрузки запустите установочный файл `.msi`. Запускается мастер установки.

3. На экране "Каталог конфигурации Apache" укажите каталог, в котором расположен файл `httpd.conf` (по умолчанию используется каталог `C:\Program Files\Apache Software Foundation\Apache<version>\conf\`). Обработка кода PHP включается автоматически.

4. При необходимости использования сервера базы данных MySQL выберите вариант "Полная установка" или выберите элементы MySQL и MySQLi в списке "Расширения".

5. После завершения установки перезапустите сервер Apache.

6. Для проверки успешности установки механизма PHP и включения обработки кода PHP в настройке Apache выполните следующие действия:

   - Откройте блокнот или любой другой текстовый редактор. Создайте файл и введите следующий текст:

     ```
     <?php 
          echo "PHP has been installed successfully!";
     ?>
     ```

   - Сохраните файл в папке htdocs с именем `test.php`. По умолчанию путь к файлу имеет вид `C:\Program Files\Apache Software Foundation\Apache<version>\htdocs\test.php`

   - Запустите браузер и введите следующий URL-адрес: `http://localhost:<port>/test.php`. Откроется следующая страница:
     ![Страница теста PHP, указывающая, что механизм PHP включен](https://netbeans.org/images_www/articles/72/php/configure-php-environment-windows/install-php-test.png)

#### Устранение проблем

1. Перезапустите сервер Apache.

2. Убедитесь, что файл настройки сервера Apache httpd.conf содержит следующие строки:

   ```
     AddType Application/x-httpd-php .php 
     LoadModule php5_module "c:/php/sapi/php5apache2_2.dll"
   ```

3. Если эти строки отсутствуют, добавьте их, сохраните `httpd.conf` и перезапустите сервер Apache.

4. Обновите страницу http://localhost:<port>/test.php.

### Сервер базы данных MySQL

Ознакомьтесь с подробными сведениями относительно [установки и настройки сервера базы данных MySQL](https://netbeans.org/kb/docs/ide/install-and-configure-mysql-server.html).

### XDebug

1. Загрузите [XDebug](http://www.xdebug.org/).
2. Установите XDebug в папку `php/`. Путь к этой папке необходим для [настройки среды](https://netbeans.org/kb/docs/php/configure-php-environment-windows_ru.html#settingUpEnvironment).

### Настройка среды

1. Если при установке используются настройки по умолчанию, обработка PHP включается автоматически.

2. Для присоединения

   ​

    

   XDebug к механизму PHP перейдите к файлу

    

   php.ini

    

   и добавьте в него следующие строки:

   Для механизма PHP 5.2 **с ориентацией на многопотоковое исполнение**:

   ```
   zend_extension_ts="<path to the php folder>/php_xdebug-<version-number>.dll"
   xdebug.remote_enable=1
   ```

   Для механизма PHP 5.2 **без ориентации на многопотоковое исполнение**:

   ```
   zend_extension_nts="<path to the php folder>/php_xdebug-<version-number>.dll"
   xdebug.remote_enable=1
   ```

   Для **любого** механизма PHP 5.3:

   ```
   zend_extension="<path to the php folder>/php_xdebug-<version-number>.dll"
   xdebug.remote_enable=1
   ```

   Некоторые пользователи считают, что необходимо включить в код следующие строки, однако другие пользователи пропускают их:

   ```
   xdebug.remote_host=127.0.0.1
   xdebug.remote_port=9000
   ; Port number must match debugger port number in NetBeans IDE Tools > Options > PHP
   xdebug.remote_handler=dbgp

   ```

   Дополнительные сведения о настройке отладчика XDebug приведена [здесь](http://www.xdebug.org/docs/install).

   **Примечание.** Убедитесь в том, что указанные пути соответствуют именам и расположению соответствующих файлов, как это определено при установке.

3. Для проверки того, что предварительно установленный механизм PHP поддерживает использование сервера базы данных MySQL выполните следующие действия:

   1. Выберите команду "Пуск" > "Панель управления".
   2. На экране "Панель управления" выберите параметр "Добавление или удаление программ".
   3. На экране "Добавление или удаление программ" перейдите к области "PHP <номер_версии>" и нажмите кнопку "Изменить". Последует запуск мастера настройки PHP. Нажмите кнопку "Далее".
   4. На экране "Изменение, исправление или удаление" выберите команду "Изменить" и нажмите кнопку "Далее".
   5. На экране "Установка веб-сервера" выберите версию сервера Apache – в рассматриваемом примере используется Apache 2.2.x Module. Нажмите кнопку "Далее".
   6. На экране "Каталог конфигурации Apache" укажите каталог, в котором расположен файл настройки Apache `httpd.conf`. Нажмите кнопку "Далее".
   7. На экране "Выбор компонентов для установки" разверните узел "Расширения" и выберите элементы MySQL и MySQLi. Нажмите кнопку "Далее".
   8. На экране "Все готово к изменению PHP <номер_версии>" выберите команду "Изменить".
   9. На экране "Мастер установки PHP <номер_версии> завершен" нажмите кнопку "Готово".

   ​

[Отправить отзыв по этому учебному курсу](https://netbeans.org/about/contact_form.html?to=3&subject=Feedback:%20Configuring%20PHP%20on%20Windows)

Для отправки комментариев и предложений, получения поддержки и новостей о последних разработках, связанных с PHP IDE NetBeans [присоединяйтесь к списку рассылки users@php.netbeans.org](https://netbeans.org/community/lists/top.html).

Возврат к учебной карте PHP