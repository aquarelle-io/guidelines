# Настройка и установка XAMPP

![img](http://design-for.net/application/maxsite/templates/default/images/date.png) 9 апреля 2012 г.![img](http://design-for.net/application/maxsite/templates/default/images/user.png) [Владимир Точилин](http://design-for.net/author/3)![img](http://design-for.net/application/maxsite/templates/default/images/post-view.png) Просмотров: 28420![img](http://design-for.net/application/maxsite/templates/default/images/rss.png) [RSS](http://design-for.net/page/nastrojka-i-ustanovka-xampp/feed)[![img](http://design-for.net/application/maxsite/templates/default/images/comments.png) ](http://design-for.net/page/nastrojka-i-ustanovka-xampp#comments)[3](http://design-for.net/page/nastrojka-i-ustanovka-xampp#comments)
![img](http://design-for.net/application/maxsite/templates/default/images/category.png) [Локальный веб сервер](http://design-for.net/category/lokalnyi-web-server) » [Программы для создания сайта](http://design-for.net/category/programmy-dlja-sajta)![img](http://design-for.net/application/maxsite/templates/default/images/tag.png) [новичкам](http://design-for.net/tag/%D0%BD%D0%BE%D0%B2%D0%B8%D1%87%D0%BA%D0%B0%D0%BC), [программы](http://design-for.net/tag/%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D1%8B)

Данная статья **Настройка и установка XAMPP** является продолжением двух статей [Установка XAMPP](http://design-for.net/page/ustanovka-veb-servera-xampp) и [Версии XAMPP](http://design-for.net/page/versii-xampp).

|      | [**Быстрый кредит**](http://design-for.net/page/bystryj-kredit)[**Микрокредит**](http://design-for.net/page/mikrokreditovanie) |
| ---- | ---------------------------------------- |
|      |                                          |

В данной статье описывается процесс настройки локального сервера XAMPP через Контрольную панель XAMPP. Обычно, **настройка XAMPP** происходит вместе с установкой.

Как правило, стандартная *установка XAMPP* на диск **С:** не представляет большой сложности. Новичкам нет никакой надобности глубоко разбираться во внутренней механике вебсервера. Ведь никто не изучает строение молотка перед употреблением по назначению. Инструмент – он и в Вебе - инструмент. Надо просто следовать инструкции.

| [**Чем свой сайт лучше**](http://design-for.net/page/chem-svoj-sajt-luchshe)[**Понятия: раскрутка продвижение оптимизация сайтов**](http://design-for.net/page/ponjatija-raskrutka-prodvizhenie-optimizacija-sajtov)[**Как написать статью на сайт**](http://design-for.net/page/kak-napisat-statju)[**Зачем создают сайты**](http://design-for.net/page/zachem-sozdajut-sajty)[**Статьи о заработке в Интернете**](http://design-for.net/page/stati-o-zarabotke-v-internete)[**Интернет заработок для новичков**](http://design-for.net/page/internet-zarabotok-dlja-novichkov) |      | [**Нерекомендуемые способы заработка через интернет**](http://design-for.net/page/nerekomenduemye-sposoby-zarabotka-cherez-internet)[**Заработок денег на кликах**](http://design-for.net/page/zarabotok-deneg-na-klikah)[**Почтовые спонсоры Рунета**](http://design-for.net/page/pochtovye-sponsory-runeta)[**MaxSite CMS**](http://design-for.net/page/maxsite-cms)[**Возможности MaxSite CMS**](http://design-for.net/page/vozmozhnosti-maxsite-cms) |
| ---------------------------------------- | ---- | ---------------------------------------- |
|                                          |      |                                          |

Ссылка на данную статью http://design-for.net/page/nastrojka-i-ustanovka-xampp

Ниже я постараюсь рассказать подробно, как происходит **настройка сервера XAMPP** и создание новой базы данных. Разбор типичных ошибок вынесен в отдельную статью Проблемы при установке XAMPP. Настройка завершится после того, как мы создадим пробный **сайт на XAMPP**.

## Необязательное

|      | 1.1. Наверно пришло время создать папку для вашего сайта, ведь все «телодвижения» мы производим лишь ради создания сайта на вашем домашнем компьютере. Вы можете создать ее, где хотите, но я создал ее в корне диска **D:** и назвал ее **designfornet**, что почти совпадает с именем этого сайта, но без точки и тире.Почему нельзя использовать для домашнего сайта имена с расширением существующих зон интернета, например, **.com** или **.ru**?По той причине, что любой ваш браузер будет искать ваш сайт mysite**.**ruили мой design-for**.**net, не внутри вашего компьютера, а в большом Интернете.Итак, запомним правила для имен внутри компьютера:– без расширений или используя несуществующие зоны, например, можно назвать сайт **mysite.local** потому, что зоны **.local** не существует;- без пробелов в одно слово (точка и тире можно).Обычно для примера используют нейтральные имена homesite или mysite, но, раз вы находитесь на моем сайте, то я думаю, имя designfornet более уместно, так как позволяет получить преемственность со статьей [Как установить MaxSite CMS на веб-сервер XAMPP](http://design-for.net/page/maxsite-cms-na-xampp), в которой речь идет о создании домашнего сайта.По-большому, имя нам нужно произвольное – лишь бы как-то назвать папку, куда мы будем копировать нулёвые файлы.1.2. Я советую Новичкам сразу сделать копию папки **xampp** где-нибудь в другом месте, а в случае фатальной ошибки – заменить всю папку или отдельный файл из сохраненной копии. Так можно сэкономить время, которое пошло бы на удаление и переустановку.Как раз для этого пригодится наша новая папка designfornet (homesite). Надо просто перетащить всю папку **xampp** (из диска **C:**) правой кнопкой мыши на/в созданную папку сайта designfornet и выбрать «Копировать». |
| ---- | ---------------------------------------- |
|      |                                          |

1.3. Еще более разумный подход состоит в следующем:

1.3.1. так как в процессе настройки мы будем вносить изменения лишь в некоторые файлы, поэтому для ускорения доступа к ним, лучше сразу установить ярлыки этих файлов на Рабочем столе.

1.3.2. если мы что-то в них напортачим, то не будем перезаливать весь мануал, а лишь заменим эти файлы нулёвыми из «неприкосновенного запаса». Экзекуцию над файлами при замене покалеченных на нулёвые можно производиться сколько угодно раз.

1.4. Поставьте рабочий браузер главным. У себя Я установил FireFox браузером по умолчанию, как самый массовый. Установите в его настройках автоматическое определение кода UTF-8.

> Сегодня у FireFox есть преимущества перед Opera и Internet Explorer: Опера стала тяжеловатой и «раздувается» при многочасовом использовании. Ослика IE используют лишь для проверки вида свежеиспеченного сайта. Ghrom догоняет по полярности FireFox среди «масс», так как имеет хорошую скорость, но еще достаточно «голый» из-за отсутствия полезных плагинов, например, политика его хозяина запрещает воровать скачивать видеоролики.

1.5. Начинающему веб мастеру для ковыряния в кодах потребуется «правильный» текстовый редактор, называемый так по той причине, что он не вносит форматирование в тексты. Поэтому нельзя использовать программу Word. Блокнот, встроенный в Windows, для редактирования кодов так же не годится. После прочтения статьи Правильные редакторы кодовых файлов надо установить на вашем компьютере [**Notepad++**](http://soft.oszone.net/program/800/Notepad/).

------

## Изучаем XAMPP Control Panel Application

2.1. Если вы продолжаете процесс установки веб сервера XAMPP, то окно контрольной панели XAMPP Control Panel Application еще перед вами. Если закрыли, то панель надо активировать через её ярлык.

[![Окно XAMPP Control Panel Application](http://design-for.net/uploads/okno-kontrolnoj-paneli-xampp.png)](http://design-for.net/uploads/okno-kontrolnoj-paneli-xampp.png)

Рис.1 Окно контрольной панели XAMPP Control Panel Application

Я надеюсь, что вы уже имеете или достали из папки **C:\xampp** на рабочий стол нужные ярлыки: **xampp_start.exe**, **xampp_stop.exe**, **xampp-control.exe**. Клик по последнему приведет к раскрытию той же панели.

> [![Ярлык XAMPP](http://design-for.net/uploads/jarlyk-xampp.png)](http://design-for.net/uploads/jarlyk-xampp.png)
> Чтобы вытащить ярлык надо открыть папку **C:\xampp** и правой кнопкой мыши потянуть ярлык на рабочий стол компьютера. После того как вы его отпустите в появившемся меню выбрать сроку «Создать ярлык».

2.2. В нижней части панели мы можем узнать о версиях панели и операционной системы, установленной на вашем компьютере, месте расположения директории самого Ксампа и его инсталлятора, и статусном состоянии панели - Check OK (запущена).

[![В нижней части панели видны версии программ и их статус](http://design-for.net/uploads/nizhnjaja-chast-kontrolnoj-paneli.png)](http://design-for.net/uploads/nizhnjaja-chast-kontrolnoj-paneli.png)

Рис.2 Нижняя часть окна панели показывает статус каждого компонета

2.3. Много, о чем я здесь пишу, не представляет интереса, потому что после настройки мы уже никогда сюда не вернемся.

В самой верхней строке панели мы видим две кнопки «**Service…**» и «**SCM…**». При помощи первой мы можем запустить XAMPP Control Panel Application как службу на своем компьютере. Вторая переносит нас на окно, в котором можно найти все службы, запущенные на нашем компьютере.

2.4. Обычно рекомендуют запускать XAMPP в качестве службы, что устраняет некоторые неприятности с совместимостью. Меня, однако, напрягает работа серверных программ, когда я не работаю с сайтом. Веб сервер у меня не имеет выхода в Интернет, поэтому я его компоненты запускают лишь по мере надобности. Тем более мне нет нужды запускать его контрольную панель в виде службы Windows.

2.5. Левый ряд квадратных полей (окошек) с именами **Svc** как раз позволяет запускать отдельные компоненты Ксампа в виде служб. Второй столбик на панели перечисляет эти компоненты. Чтобы они не включались и не работали постоянно вместе с Windows - оставляйте эти поля пустыми.

2.6. Третий столбик состоит из кнопок запуска – **Start**. Мы уж договорились, что для нас важными являются **Apache** и **MySql**, а ftp–клиент **FileZilla** и почтовый клиент **Mercuri** нам пока не нужны.

2.7. Нажмем на кнопку **Start** напротив **Apache**. Если все нормально установилось, то загорится зеленая кнопка с надписью **Running** (запущено), а надпись **Start** сменится на **Stop**.

Подобным образом запускаем два основных компонента веб сервера – **Apache** и **MySql**.

[![В панели можно видеть запущенные компоненты и их статус](http://design-for.net/uploads/vidno-sostojanie-komponentov-i-porty-kotorye-oni-zanimajut.png)](http://design-for.net/uploads/vidno-sostojanie-komponentov-i-porty-kotorye-oni-zanimajut.png)

Рис.3 После запуска компонента можно видеть не только его статус, но занятый им порт

2.8. В зависимости от версии вид Контрольной панели может отличаться, обычно наличием или отсутствием кнопок в самом правом столбце. По этой причине варианты настройки могут несколько отличаться. Я думаю, вы просто пропустите пункты, которые не касаются вашей версии XAMPP

В более ранних версиях XAMPP присутствуют кнопки «**Shell**», «**Setup**», «**Port-Check**».

2.9. Вспоминаем, что для нас веб-сервер XAMPP - программа проходная. Мы опробовать скрипты на нем не будем, как только установим, так сразу и забудем. Поэтому с кнопками надо только познакомимся, так как пользоваться ими, если и придется, то только разок. Если у вас некоторых кнопок нет, то пропускаете соответствующие пункты статьи.

2.10. Кнопка «**Shell**» - запускает командную строку Windows, работать в которой для пользователя этой операционной системы несколько непривычно, а новичкам – тем более.

2.11. Кнопка «**Setup**» возвращает нас к пункту установки через командную строку, когда можно включить или выключить любой модуль XAMPP выставкой определенного числа. Можно использовать, если у вас включен лишний модуль (**Perl**). Вас сюда еще вернут, если что-то будут не так, как хочет установщик программы.

2.12. Кнопка «**Port-Check**» проверяет свободен или **занят порт 80**, необходимые для работы сервера **Apache**. **Порт 80** часто используют некоторые службы Windows, но чаще всего **порт 80** занимает такая популярная программа, как **Skype**.

Если у вас **занят порт 80** другой программой, то не запустится ядро вебсерера XAMPP - программа сервер **Apache**. О том как **освободить порт 80** вы можете узнать в статье Проблемы при установке XAMPP. После **открытия порта 80** вернитесь к данной статье для продолжения настройки Ксампа.

2.13. Последний ряд кнопок носит вспомогательный характер, потом вы сами их можете понажимать ради интереса.

Наc больше интересуют кнопки **Admin** в одном ряду с запущенными компонентами.

При первом запуске может появиться окно, в котором можно выбрать язык для XAMPP. Русского там нет – поэтому выбираем английский – **English**.

[![Страница XAMPP для выбора языка](http://design-for.net/uploads/okno-dlja-vybora-jazyka.png)](http://design-for.net/uploads/okno-dlja-vybora-jazyka.png)

Рис.4 Окно для выбора языка

2.14. Когда вы нажмете на кнопку **Admin** в ряду с **Apache**, то запустится ваш основной браузер, в окне которого вы увидите страницу приветствия «**Welcome to XAMPP for Windows!**» с адресом http://localhost/xampp/.

[![Окно приветствия XAMPP](http://design-for.net/uploads/okno-privetstvija-xampp.png)](http://design-for.net/uploads/okno-privetstvija-xampp.png)

Рис.5 Страница приветствия XAMPP

2.15. Текст под приветствием «**Welcome to XAMPP for Windows!**» нам малоинтересен, но в строке «For OpenSSL support please use the test certificate with https://127.0.0.1 or https://localhost» нам предлагают перейти по ссылке и получить сертификат, а заодно выполнить идентификацию адресов в браузере.

Кликаем по первой ссылке https://127.0.0.1. Пока браузер не знает адрес XAMPP он считает соединение недоверенным. После перехода в браузере выбираем «**Я понимаю риск**» и нажимаем на «**Добавить исключения**».

[![Панель предупреждения от браузера о недостоверном соединении](http://design-for.net/uploads/mini/esli-brauzer-bastuet-to-nado-dobavit-v-iskljuchenija.png)](http://design-for.net/uploads/esli-brauzer-bastuet-to-nado-dobavit-v-iskljuchenija.png)

Рис.6 Пробираемся через установки браузера, чтобы внести страницу XAMPP в исключения

На следующей вкладке получаем доверенный идентификатор и подтверждаем исключение безопасности.

[![Получаем сертификат и разрешаем исключение](http://design-for.net/uploads/mini/izmenjaem-dlja-brauzera-identifikaciju-sajta.png)](http://design-for.net/uploads/izmenjaem-dlja-brauzera-identifikaciju-sajta.png)

Рис.7 В браузере делаем исключение для адреса XAMPP

2.16. Остальную настройку мы будем выполнять, переходя по ссылкам, которые находятся в левой колонке (сайдбаре) на страницах XAMPP.

Главными для нас будут «**Status**», «**Security**», **phpMyAdmin**». Любознательные могут посмотреть остальные ссылки сами.

[![В левой колонке находятся ссылки для настроек XAMPP](http://design-for.net/uploads/ssylki-na-stranicy-nastroek-xampp.png)](http://design-for.net/uploads/ssylki-na-stranicy-nastroek-xampp.png)

Рис.8 На левой стороне страницы видны ссылки настроек

2.17. Для перехода к управляющей утилите XAMPP надо кликнуть по ссылке **phpMyAdmin**. Откроется страница, в центре которой имеется форма для заполнения двух полей: первое поле для ввода названия базы нашего сайта, второе - для кодировки.

[![Страница утилиты phpMyAdmin для создания новой базы MySql](http://design-for.net/uploads/stranica-phpmyadmin-.png)](http://design-for.net/uploads/stranica-phpmyadmin-.png)

Рис.9 На странице phpMyAdmin нам надо заполнить два поля.

2.18. Вставляем в первом поле, над которым написано **Новая база данных**, имя своего сайта **designfornet** (я думаю, логично, что имя базы совпадает с именем сайта).

Для заполнения второго поля есть указатель в конце прямоугольника формы, по нажиму на который появится список кодировок. Надо опуститься до строки **utf8_generai-ci** и, кликнув по ней, закрепить эту кодировку в форме.

[![Вставляем имя новой базы и выбираем кодировку](http://design-for.net/uploads/pole-dlja-vvoda-imeni-bazy-i-kodirovki.png)](http://design-for.net/uploads/pole-dlja-vvoda-imeni-bazy-i-kodirovki.png)

Рис.10 В пустые поля вставляем имя и выбираем кодировку база

2.19. После нажатия на кнопку «Сохранить» база с именем **designfornet** будет создана.

[![Сообщение о создании базы disignfornet](http://design-for.net/uploads/baza-disignfornet.png)](http://design-for.net/uploads/baza-disignfornet.png)

Рис.11 Подтверждение о создании базы **disignfornet**

2.20. Следом нам надо создать пользователей этой базы и задать им пароли доступа. Нажмем на ссылку Привилегии вверху страницы.

[![Список пользователей базой по умолчанию](http://design-for.net/uploads/spisok-polzovatelej.png)](http://design-for.net/uploads/spisok-polzovatelej.png)

Рис.12 Страница со списком предустановленных пользователей

Как оказывается, XAMPP уже создал нам пару пользователей с одинаковыми именами **root**.

> Собственно, это один пользователь в двух лицах, но система будет нам активировать одно лицо по ссылке 127.0.0.1, а другое - по localhost.

2.21. Для создания пароля первому пользователю **root** кликаем по значку «Редактировать» в крайнем столбце «Действие». В открывшейся странице опускаемся до блока «Изменить пароль».

[![Задаем пароль для пользователя root](http://design-for.net/uploads/zadaem-parol.png)](http://design-for.net/uploads/zadaem-parol.png)

Рис.13 Блок «Изменить пароль»

У себя я использовал пароль в виде того же имени «**root**», что делает его самым простым.

> Пользователи, которые собирается открывать XAMPP для Интернета могут генерировать сложный пароль, для чего есть кнопка внизу.

2.22. После клика по кнопке «OK» появится страница с подтверждением создания пароля для первого **root**.

[![Подтверждение создания пароля для первого root](http://design-for.net/uploads/podtverzhdenie-sozdanija-parolja.png)](http://design-for.net/uploads/podtverzhdenie-sozdanija-parolja.png)

Рис. 14 Окно с подтверждение о создании пароля

2.23. Для создания пароля для второго пользователя нажимаем на ссылку Привилегиивверху страницы. Кликаем по значку «Редактировать» и повторяем процедуру создания пароля.

[![Переходим к редактированию второго root](http://design-for.net/uploads/mini/stranca-privilegii-.png)](http://design-for.net/uploads/stranca-privilegii-.png)

Рис.15. Повторяем регистрацию пароля для второго root

Как видите и для него я выставил пароль **root**, совпадающий с его именем.

[![Создаем пароль для второго пользователя root](http://design-for.net/uploads/mini/sozdaem-vtoroj-parol-.png)](http://design-for.net/uploads/sozdaem-vtoroj-parol-.png)

Рис.16 Пароль выставляем тот же - root

2.24. После установки паролей для **root** вернемся по ссылке Привилегии, где в списках мы можем обнаружить лишних пользователь, которых надо удалить. Выставляем напротив такого пользователя галочку и выбираем действие «Удалить выделенных пользователей».

[![Удаление лишних пользователей](http://design-for.net/uploads/mini/udalenie-polzovatelej.png)](http://design-for.net/uploads/udalenie-polzovatelej.png)

Рис. 17 Страница со списком пользователей

После всех телодвижений у нас должно остаться три пользователя: **pma** (пользователь от системы) и два одинаковых - **root**, с одинаковыми паролями.

2.25. Теперь для сохранения всех наших установок требуется перезагрузить XAMPP, для чего находим на Рабочем столе ярлык **xampp_stop.ex**e. После клика по нему появиться и исчезнет черное окно командной строки. Следом надо кликнуть по ярлыку **xampp_start.exe**и закрыть черное окно с предупреждением, чтобы мы запускали Start перед Stop. Однако проще запустить Apache и MySql через кнопки Контрольной панели XAMPP и сразу перейти по «**Admin**»

2.26. Нажимаем на Контрольной панели кнопку «**Admin**» для повторного входа в XAMPP. Переходим по ссылке **Status** на страницу, в которой видны запущенные компоненты.

[![Видны запущенные компоненты](http://design-for.net/uploads/mini/okno-status1.png)](http://design-for.net/uploads/okno-status1.png)

Рис. 18 Страница **Status**

2.27. Намного интереснее страница по ссылке **Security**, на которой мы видим предупреждения о проблемах с компонентами XAMPP. Все проблемы, касающиеся нас, я выделил на рисунке в прямоугольники. Как видно, одну проблему мы преодолели.

[![Страница с таблицей предупреждений](http://design-for.net/uploads/mini/stranica-security.png)](http://design-for.net/uploads/stranica-security.png)

Рис. 19 Страница **Security**

> Чтобы сделать быстрый перевод, нужно скопировать английские фразы в форму на странице [онлайн переводчика](http://www.translate.ru/).

Суть проблемы в свободном доступе из внешней сети, для решения которой следует перейти по ссылке http://localhost/security/xamppsecurity.php, расположенной под таблицей с предупреждениями.

2.28. На открывшейся странице **Security console MySQL & XAMPP** следует вставить любимое **root** во все формы. Кроме того, можно указать, чтобы Ксамп создал документы, в которых будут храниться пароли.

[![Вставляем любимое root во все формы](http://design-for.net/uploads/security-console.png)](http://design-for.net/uploads/security-console.png)

Рис.20 Страница **Security console MySQL & XAMPP**

2.29. После выставки паролей требуется перезагрузить XAMPP. Повторяем все как в пункте 2.25. и переходим по ссылке **Security** для проверки оставшихся проблем.

[![Компоненты настроены](http://design-for.net/uploads/stranica-security-posle-nastrojki.png)](http://design-for.net/uploads/stranica-security-posle-nastrojki.png)

Рис.21 Страница **Security** после установки паролей

Как видно из Рис.21 основные компоненты запущены и для них созданы пользователи с правами доступа.

> Другое дело, что я везде вставлял любимое **root**, так как на домашнем компьютере нет смысла создавать сложные пароли. Я уже писал, что XAMPP не предназначен для промышленного использования, а в домашней сети сложные пароли только создают дополнительные сложности.

На этом можно считать настройку XAMPP законченной, что правда, не означает создание автоматически нашего сайта **designfornet**.

Как я сказал в начале статьи, настройку веб сервера XAMPP мы закончим после создания пробного сайта.

Для этого вам нужно будет перейти к статье Сайт на XAMPP.

![twitter.com](http://design-for.net/application/maxsite/plugins/addzakl/images/twitter.png)

 

![facebook.com](http://design-for.net/application/maxsite/plugins/addzakl/images/facebook.png)

 

![vkontakte.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/vkontakte.png)

 

![odnoklassniki.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/odnoklassniki.png)

 

![mail.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/mail-ru.png)

 

![ya.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/yaru.png)

 

![rutvit.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/rutvit.png)

 

![myspace.com](http://design-for.net/application/maxsite/plugins/addzakl/images/myspace.png)

 

![technorati.com](http://design-for.net/application/maxsite/plugins/addzakl/images/technorati.png)

 

![digg.com](http://design-for.net/application/maxsite/plugins/addzakl/images/digg.png)

 

![friendfeed.com](http://design-for.net/application/maxsite/plugins/addzakl/images/friendfeed.png)

 

![pikabu.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/pikabu.png)

 

![blogger.com](http://design-for.net/application/maxsite/plugins/addzakl/images/blogger.png)

 

![liveinternet.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/liveinternet.png)

 

![livejournal.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/livejournal.png)

 

![memori.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/memori.png)

 

![google.com](http://design-for.net/application/maxsite/plugins/addzakl/images/google-bookmarks.png)

 

![bobrdobr.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/bobrdobr.png)

 

![mister-wong.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/mister-wong.png)

 

![yahoo.com](http://design-for.net/application/maxsite/plugins/addzakl/images/yahoo-bookmarks.png)

 

![yandex.ru](http://design-for.net/application/maxsite/plugins/addzakl/images/yandex.png)

 

![del.icio.us](http://design-for.net/application/maxsite/plugins/addzakl/images/delicious.png)

 

- Локальный веб сервер
  - [Веб сервер на своем компьютере](http://design-for.net/page/veb-server-na-svoem-kompjutere)
  - [Установка XAMPP](http://design-for.net/page/ustanovka-veb-servera-xampp)
  - [Сервер XAMPP](http://design-for.net/page/server-xampp)
  - [Версии XAMPP](http://design-for.net/page/versii-xampp)
  - Настройка и установка XAMPP
  - [Пример создания сайта на XAMPP](http://design-for.net/page/primer-sozdanija-sajta)
  - [Настройка виртуальных хостов](http://design-for.net/page/nastrojka-virtualnyh-hostov)