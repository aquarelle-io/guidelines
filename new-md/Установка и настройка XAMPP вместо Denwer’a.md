# Установка и настройка XAMPP вместо Denwer’a

[Главная](https://masalkin.name/) » [Создание сайтов](https://masalkin.name/sozdanie-sajtov/) » Установка и настройка XAMPP вместо Denwer’a

![img](https://masalkin.name/wp-content/uploads/2015/07/09.jpg)

26ИЮЛЯ2015

СОЗДАНИЕ САЙТОВ

НОВИЧКАМ, ХОСТИНГ

16485

[45](https://masalkin.name/ustanovka-i-nastrojka-xampp-vmesto-denwer-a/#comments)

##### ПОДЕЛИСЬ ЭТОЙ ЗАПИСЬЮ

Facebook

Twitter

Мой мир

Вконтакте

Одноклассники

Google+

Денвером я пользовался три с лишним года, до определенного момента. Он просто отказался работать, постоянно выдавал белый экран и все. Сколько не пробовал его реанимировать так и не удалось. Так эта загадка и осталась у меня не разгаданной, все те рекомендации которые мне предлагали на форуме Denwer’a мне не помогли. После этого я начал искать альтернативу, и нашел отличный вариант. Как по мне, XAMPP намного удобнее в плане управления, так же обновляется гораздо чаще денвера.

## И так что это такое XAMPP?

XAMPP – это кросплатформенная сборка веб-сервера. Ее можно установиться на Linux, Windows, Mac OS и даже Solaris. Денвер же работает только под Windows. В состав данной сборки входят Apache, MySQL, PHP обработчик.

И так, для того чтобы скачать себе XAMPP переходим [по этой ссылке](https://www.apachefriends.org/ru/download.html), и качаем тот вариант дистрибутива, что вам подходит.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/1.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/1.png)

Большинство из вас пользуется операционной системой Windows. поэтому хочу предупредить, что Windows XP и Win2003, ну и более старые варианты OS, не поддерживаются. На таких древних динозавров ставьте Денвер.

После того как скачаете дистрибутив, переходим к его установке. Думаю особых трудностей установка XAMPP у вас вызвать не должна. Запускаем исполняемый файл.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/2.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/2.png)

После чего выбираем компоненты которе устанавливаем.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/3.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/3.png)

Включаем все чекбоксы, тем самым сообщаем что хотим установить Apache, MySQL, файловый менеджер Fizilla, почтовый сервер Mercury и сервер Tomcat и жмем кнопку далее.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/4.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/4.png)

Указываем место установки. По умолчанию это диск С:/xampp

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/5.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/5.png)

Отключаем чекбокс, узнать подробнее о Bitnami, и жмем далее.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/6.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/6.png)

Финишируем и запускаем панель управления XAMPP.

## Пробежимся по панели управления XAMPP

В сравнении с более древними версиями она претерпела ряд изменений. Теперь она выглядит вот так:

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/7.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/7.png)

а раньше выглядела вот так:

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/8.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/8.png)

Сейчас нас с вами интересует кнопка Config что находится справа вверху. Можете на нее нажать, и сделать точно такие же настройки как у меня.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/9.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/9.png)

Суть настроек следующая. При запуске панели XAMPP сразу же запускать апач, mysql сервер, а так же почтовый сервер mercury.

Дальше стоят чекбоксы, использовать дефолтные порты при запуске, и показывать дебаг информацию.

В качестве редактора, выбран блокнот. Поле с браузером пустое, вы можете выбрать свой браузер. По умолчанию у меня система использует мозилу, поэтому я прописывать ничего не стал.

**Кнопка Netstat** — если на нее нажать, можете увидеть какие порты сейчас используются системой.

**Кнопка Shell** — вызовет командную строку.

**Explorer** — откроет папку куда установлен XAMPP.

**Service** — открывает окно, где отображены все действующие на данный момент службы.

**Help и Quit** объяснять думаю не нужно.

И так, с панелью управления мы познакомились. Теперь запускаем модули Апача и MySQL.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/10.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/10.png)

Открываем браузер, и вбиваем в адресную строку localhost. Наблюдаем за страницей приветствия.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/11.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/11.png)

Все хорошо, все работает.

Чтобы попасть в phpMyAdmin и создать там базу данных, вы открываете панель управления и напротив службы MySQL жмете на кнопку admin. Вам сразу же откроется нужная страница в браузере.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/12.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/12.png)

Чтобы создать свой сайт на сервере XAMPP, вам необходимо в папке C:\xampp\htdocs создать папку, например wordpress, чтобы в дальнейшем вы могли обращаться к данному сайту по адресу http://localhost/wordpress/

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/13.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/13.png)

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/14.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/14.png)

Для этого открываем вновь панель управления XAMPP и жмем кнопку Explorer. Находим нужную папку, и заливаем туда файлы движка.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/15.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/15.png)

После чего переходим по адресу http://localhost/wordpress/ и смело можем начинать установку WordPress движка на свою локальную машину.

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/16.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/16.png)

## Настройки PHP обработчика.

Перед тем как создавать свой первый сайт на локалке, давайте внесем некоторые изменения в конфигурационный файл php.ini

Для этого в панели управления на против модуля Апач, жмем кнопку config и в выпадающем списке выбираем файл php.ini

[![Установка и настройка XAMPP](https://masalkin.name/upload/image_post/create/2015/07/26/small/17.png)](https://masalkin.name/upload/image_post/create/2015/07/26/big/17.png)

Ищем строчку **memory_limit** и меняем ее значение на 256M, тем самым мы указываем сколько памяти выделять на обработку php скриптов.

Вы можете спросить почему именно 256 мегабайт, все просто, [мой хостинг предоставляет](https://masalkin.name/kak-vy-brat-hosting-dlya-sajta-kakoj-hosting-vy-brat) мне именно такое количество памяти. Поэтому я стараюсь максимально приблизить настройки локальной машины, к настройкам полевых испытаний.

Теперь поднимитесь глазами чуть выше, и найдите строку **max_execution_time**, там поставьте значение в 180 секунд.

Дальше ищите **post_max_size** и меняйте его значение на 999 мегабайт. Данная манипуляция позволит прикреплять к постам файлы размером до 999 мегабайт. Сохраняем изменения.

Теперь после всех настроек сервера XMAPP перезагружаем Apache.

В качестве P.S. хочу сказать что ни сколько не жалею, что перешел с Denwer’a на XAMPP. Он мне нравится на много больше и работает как мне кажется шустрее.

### Черкни и ты пару строк

А вы каким софтом пользуетесь для работы с локальной машины? Пробовали ли денвер? Или сразу перешли на XAMPP? Есть ли какие-то сложности по установке или настройке локального сервера?

[НОВИЧКАМ](https://masalkin.name/tag/novchikam/)[ХОСТИНГ](https://masalkin.name/tag/hosting/)