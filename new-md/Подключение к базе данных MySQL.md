# Подключение к базе данных MySQL

В этом документе показано, как настроить соединение с базой данных MySQL из среды IDE NetBeans. После подключения вы можете начать работу с MySQL в среде Database Explorer, создавая новые базы данных и таблицы, заполняя таблицы данными и запуская SQL-запросы по структурам и контенту базы данных. Этот учебник предназначен для новичков с базовым пониманием управления базой данных, которые хотят применить свои знания для работы с MySQL в среде IDE NetBeans.

[MySQL](http://www.mysql.com/) - популярная система управления реляционными базами данных с открытым исходным кодом (RDBMS), обычно используемая в веб-приложениях из-за ее скорости, гибкости и надежности. MySQL использует SQL или *Structured Query Language* для доступа и обработки данных, содержащихся в базах данных.

**Ожидаемая продолжительность: 30 минут**

**содержание**

- [Настройка свойств сервера MySQL](https://netbeans.org/kb/docs/ide/mysql.html#configuring)
- [Запуск сервера MySQL](https://netbeans.org/kb/docs/ide/mysql.html#starting)
- [Создание и подключение к базе данных](https://netbeans.org/kb/docs/ide/mysql.html#connectingDB)
- [Создание таблиц базы данных](https://netbeans.org/kb/docs/ide/mysql.html#creating)
- [Работа с данными таблицы](https://netbeans.org/kb/docs/ide/mysql.html#working)
- [Запуск сценария SQL](https://netbeans.org/kb/docs/ide/mysql.html#running)
- [Смотрите также](https://netbeans.org/kb/docs/ide/mysql.html#seeAlso)

**Чтобы следовать этому руководству, вам необходимо следующее программное обеспечение и ресурсы.**

| Программное обеспечение или ресурс       | Требуется версия                         |
| ---------------------------------------- | ---------------------------------------- |
| [Сетевая среда NetBeans](https://netbeans.org/downloads/index.html) | 7.2, 7.3, 7.4, 8.0, Java                 |
| [Java Development Kit (JDK)](http://www.oracle.com/technetwork/java/javase/downloads/index.html) | Версия 7 или 8                           |
| Сервер базы данных MySQL                 | [Версия 5.x](http://dev.mysql.com/downloads/mysql/) |

**Примечание. В** этом учебнике предполагается, что на вашем компьютере установлена и настроена СУБД MySQL. Если вы устанавливаете в первый раз, обратитесь за помощью к официальной [документации](http://dev.mysql.com/doc/refman/5.0/en/installing-cs.html) по [MySQL](http://dev.mysql.com/doc/refman/5.0/en/installing-cs.html). Вы также можете обратиться к [разделу Настройка сервера баз данных MySQL в операционной системе Windows](https://netbeans.org/kb/docs/ide/install-and-configure-mysql-server.html) .

## Настройка свойств сервера MySQL

NetBeans IDE поставляется в комплекте с поддержкой СУБД MySQL. Прежде чем вы сможете получить доступ к серверу баз данных MySQL в среде IDE NetBeans, вы должны настроить свойства сервера MySQL.

1. Щелкните правой кнопкой мыши узел «Базы данных» в окне «Службы» и выберите «Зарегистрировать сервер MySQL», чтобы открыть диалоговое окно «Свойства сервера MySQL».
   ![Диалоговое окно «Свойства сервера MySQL»: основные свойства](https://netbeans.org/images_www/articles/73/ide/mysql/mysql-props1.png)

2. Убедитесь, что имя и порт хоста сервера верны.

   Обратите внимание, что IDE входит в `localhost`качестве имени хоста сервера по умолчанию и `3306`в качестве номера порта сервера по умолчанию.

3. Введите имя пользователя администратора (если не отображено).

   **Примечание.** Для создания и удаления баз данных необходим административный доступ.

4. Введите пароль администратора. Значение по умолчанию - пустое.

   **Примечание.** Пустым паролем может быть также пароль.

5. Перейдите на вкладку «Свойства администратора» в верхней части диалогового окна.

   Затем отображается вкладка «Свойства администратора», позволяющая вводить информацию для управления сервером MySQL.

6. В поле «Путь / URL-адрес для администратора» введите или перейдите к местоположению вашего приложения администрирования MySQL, такого как инструмент администрирования MySQL, PhpMyAdmin или другие средства администрирования через Интернет.

   **Примечание.**`mysqladmin` Средство администрирования MySQL находится в `bin`папке установочного каталога MySQL. Это инструмент командной строки и не идеален для использования с IDE.

   Введите аргументы для инструмента admin в поле «Аргументы».

7. В команде Путь к началу введите или перейдите к расположению команды запуска MySQL. Чтобы найти команду запуска, найдите `mysqld`в `bin`папке установочного каталога MySQL.

   **Примечание** . Рекомендуемый двоичный код для Unix и NetWare `mysql_safe`. Команда запуска также может быть изменена, если MySQL был установлен как часть установки AMP.

   Введите любые аргументы для команды start в поле «Аргументы».

8. В поле «Путь к остановке» введите или просмотрите местоположение команды остановки MySQL. Обычно это путь `mysqladmin`в `bin`папку установочного каталога MySQL. Если команда `mysqladmin`, в поле Аргументы типа `-u root stop`для предоставления `root`прав доступа для остановки сервера.

9. По завершении вкладка «Свойства администратора» будет напоминать следующий рисунок. Если вы настроены с вашей конфигурацией, нажмите «ОК».

   ​

## Запуск сервера MySQL

Прежде чем вы сможете подключиться к серверу баз данных MySQL, вы должны сначала убедиться, что сервер баз данных MySQL запущен на вашем компьютере. Если сервер базы данных не подключен, вы увидите **(отключен)** рядом с именем пользователя в узле MySQL Server в окне «Сервис», и вы не сможете расширить узел.

Чтобы подключиться к серверу базы данных, убедитесь, что на вашем компьютере запущен сервер баз данных MySQL, щелкните правой кнопкой мыши узел «Базы данных»> «Сервер MySQL» в окне «Службы» и выберите «Подключиться». Возможно, вам будет предложено предоставить пароль для подключения к серверу.

Когда сервер подключен, вы сможете расширить узел MySQL Server и просмотреть все доступные базы данных MySQL.

## Создание и подключение к экземпляру базы данных

Общим способом взаимодействия с базами данных является редактор SQL. Для этой цели среда IDE NetBeans имеет встроенный редактор SQL. Редактор SQL, как правило, доступен с помощью команды Execute Command из контекстного меню узла соединения (или дочерних узлов узла подключения). Теперь, когда вы подключены к серверу MySQL, вы можете создать новый экземпляр базы данных с помощью редактора SQL. В этом уроке создайте экземпляр `MyNewDatabase` :

1. В окне «Службы» IDE щелкните правой кнопкой мыши узел «Сервер MySQL» и выберите «Создать базу данных».

   Откроется диалоговое окно «Создать базу данных MySQL».

2. В диалоговом окне «Создать базу данных MySQL» введите имя новой базы данных. Мы будем использовать 

   ```
   MyNewDatabase
   ```

   этот учебник. Оставьте флажок не выбранным в это время. 

   ​

   ​

   **Примечание.** Вы также можете предоставить полный доступ к данному пользователю. По умолчанию только пользователь admin имеет права на выполнение определенных команд. Выпадающий список позволяет назначать эти разрешения указанному пользователю.

3. Нажмите «ОК».

   Новая база данных отображается в узле MySQL Server в окне «Службы».

4. Щелкните правой кнопкой мыши новый узел базы данных и выберите «Подключить» во всплывающем меню, чтобы открыть соединение с базой данных.

   Открытые соединения с базой данных представлены полным узлом соединения ( ![Значок полного узла подключения](https://netbeans.org/images_www/articles/73/ide/mysql/connection-node-icon.png)) в окне «Службы».

## Создание таблиц базы данных

Теперь, когда вы подключились к `MyNewDatabase` , вы можете начать изучать, как создавать таблицы, заполнять их данными и изменять данные, хранящиеся в таблицах. Это позволяет вам более подробно изучить функциональность, предлагаемую Database Explorer, а также поддержку IDE NetBeans для файлов SQL.

`В` настоящее время `MyNewDatabase` пуст. В среде IDE можно добавить таблицу базы данных либо с помощью диалогового окна «Создать таблицу», либо путем ввода SQL-запроса и запуска его непосредственно из редактора SQL. В следующих упражнениях вы будете использовать редактор SQL для создания `Counselor` таблицы и диалогового окна Создать таблицу для создания `Subject`таблицы. После создания таблиц вы запустите SQL-скрипт для заполнения таблиц.

1. [Использование редактора SQL](https://netbeans.org/kb/docs/ide/mysql.html#usingSQLEditor)
2. [Использование диалогового окна «Создать таблицу»](https://netbeans.org/kb/docs/ide/mysql.html#usingCreateTable)

### Использование редактора SQL

В этом упражнении вы будете использовать редактор SQL для создания `Counselor`таблицы.

1. В Проводнике базы данных разверните узел подключения `MyNewDatabase` ( ![Значок узла подключения](https://netbeans.org/images_www/articles/73/ide/mysql/connection-node-icon.png)) и обратите внимание, что есть три подпапки: Таблицы, Представления и Процедуры.

2. Щелкните правой кнопкой мыши папку «Таблицы» и выберите «Выполнить команду». Пустой холст открывается в редакторе SQL в главном окне.

3. В редакторе SQL введите следующий запрос. Это определение таблицы для таблицы 

   советника, которую

    вы собираетесь создать.

   ```
   CREATE TABLE Советник (
       Id SMALLINT UNSIGNED NOT NULL AUTO_INCREMENT,
       FirstName VARCHAR (50),
       NickName VARCHAR (50),
       LastName VARCHAR (50),
       Телефон VARCHAR (25),
       Email VARCHAR (50),
       MemberSince DATE DEFAULT '0000-00-00',
       ПЕРВИЧНЫЙ КЛЮЧ (id)
               );
   ```

   Примечание.

    Запросы, сформированные в редакторе SQL, обрабатываются на языке структурированных запросов (SQL). SQL придерживается строгих правил синтаксиса, которые вы должны знать при работе в редакторе IDE. При запуске запроса в окне «Вывод» генерируется обратная связь от механизма SQL, указывающая, выполнено ли выполнение или нет.

4. Чтобы выполнить запрос, нажмите кнопку «Запустить SQL» ( ![Запустить кнопку SQL](https://netbeans.org/images_www/articles/73/ide/mysql/run-sql-button.png)) на панели задач вверху (Ctrl-Shift-E) или щелкните правой кнопкой мыши в редакторе SQL и выберите «Выполнить». IDE создает таблицу `консультантов` в базе данных, и в окне вывода появляется сообщение, подобное приведенному ниже. 
   ![Окно вывода показывает успешное выполнение](https://netbeans.org/images_www/articles/73/ide/mysql/create-counselor-query.png)

5. Чтобы проверить изменения, щелкните правой кнопкой мыши узел «Таблицы» в проводнике базы данных и выберите «Обновить». Параметр Refresh обновляет компонент пользовательского интерфейса Database Explorer до текущего состояния указанной базы данных. Обратите внимание, что новый узел таблицы `консультантов` ( ![Значок узла таблицы](https://netbeans.org/images_www/articles/73/ide/mysql/table-node.png)) теперь отображается под таблицами в проводнике базы данных. Если вы расширяете узел таблицы, вы можете увидеть созданные вами столбцы (поля), начиная с первичного ключа ( ![Значок основного ключа](https://netbeans.org/images_www/articles/73/ide/mysql/primary-key-icon.png)).

   ​

### Использование диалогового окна «Создать таблицу»

В этом упражнении вы будете использовать диалоговое окно «Создать таблицу», чтобы создать `Subject`таблицу.

1. В проводнике базы данных щелкните правой кнопкой мыши узел «Таблицы» и выберите «Создать таблицу». Откроется диалоговое окно «Создать таблицу».

2. В текстовом поле Имя таблицы введите `Subject` .

3. Нажмите «Добавить столбец».

4. Для имени столбца введите `идентификатор` . Выберите `тип SMALLINT` для типа данных в раскрывающемся списке Тип. Нажмите «ОК».
   ![Снимок экрана диалогового окна «Добавить столбец»](https://netbeans.org/images_www/articles/73/ide/mysql/add-column-dialog.png)

5. Установите флажок «Первичный ключ» в диалоговом окне «Добавить столбец». Вы указываете первичный ключ для своей таблицы. Все таблицы, найденные в реляционных базах данных, должны содержать первичный ключ. Обратите внимание, что при выборе флажка «Ключ» автоматически выбираются флажки «Индекс» и «Уникальный», а флажок «Нуль» отменяется. Это связано с тем, что первичные ключи используются для идентификации уникальной строки в базе данных и по умолчанию образуют индекс таблицы. Поскольку все строки должны быть идентифицированы, первичные ключи не могут содержать значение Null.

6. Повторите эту процедуру, добавив оставшиеся столбцы, как показано в следующей таблице.

   | ключ        | Индекс      | Ноль        | уникальный  | Название столбца | Тип данных | Размер |
   | ----------- | ----------- | ----------- | ----------- | ---------------- | ---------- | ------ |
   | [Проверено] | [Проверено] |             | [Проверено] | Я бы             | SMALLINT   | 0      |
   |             |             | [Проверено] |             | имя              | VARCHAR    | 50     |
   |             |             | [Проверено] |             | описание         | VARCHAR    | 500    |
   |             |             | [Проверено] |             | FK_counselorID   | SMALLINT   | 0      |

   Вы создаете таблицу с именем `Subject,` которая будет хранить данные для каждой из следующих записей.

   - **Имя:** название темы
   - **Описание:** описание предмета
   - **Идентификатор советника: идентификатор** консультанта, соответствующий идентификатору из таблицы советника

   ​

   Убедитесь, что поля в диалоговом окне «Создать таблицу» соответствуют показанным выше, а затем нажмите «ОК». IDE генерирует `Subject` таблицу в базе данных, и вы можете увидеть новый `Subject` узел таблицы ( ![Значок узла таблицы](https://netbeans.org/images_www/articles/73/ide/mysql/table-node.png)) немедленно вывести под таблицей в Database Explorer.

## Работа с данными таблицы

Для работы с табличными данными вы можете использовать редактор SQL в среде IDE NetBeans. Запустив SQL-запросы в базе данных, вы можете добавлять, изменять и удалять данные, хранящиеся в структурах базы данных. Чтобы добавить новую запись (строку) в таблицу `советника` , выполните следующие действия:

1. Выберите команду «Выполнить команду» из папки «Таблицы» в «Проводнике базы данных». Пустой холст открывается в редакторе SQL в главном окне.

2. В редакторе SQL введите следующий запрос.

   ```
   ВСТАВИТЬ В Советник
   ЦЕННОСТИ (1, «Рикки», «Дракон», «Стимбоат», «334 612-5678», «r_steamboat@ifpwafcad.com», «1996-01-01»)
   ```

3. Чтобы выполнить запрос, щелкните правой кнопкой мыши в редакторе SQL и выберите «Выполнить». В окне «Вывод» вы увидите сообщение о том, что запрос был успешно выполнен.

4. ​

   Чтобы проверить, что новая запись была добавлена в таблицу `советника` , в Проводнике базы данных щелкните правой кнопкой мыши узел таблицы `консультантов` и выберите «Просмотр данных». В главном окне открывается новая панель редактора SQL. Когда вы выбираете View Data, запрос на выбор всех данных из таблицы автоматически создается в верхней части редактора SQL. Результаты инструкции отображаются в виде таблицы в нижней области. В этом примере отображается таблица `советника` . Обратите внимание, что новая строка была добавлена с данными, которые вы только что предоставили из SQL-запроса.

   ​

## Запуск сценария SQL

Другим способом управления табличными данными в среде IDE NetBeans является запуск внешнего сценария SQL непосредственно в среде IDE. Если вы создали сценарий SQL в другом месте, вы можете просто открыть его в среде IDE NetBeans и запустить его в редакторе SQL.

В демонстрационных целях загрузите файл [ifpwafcad.sql](https://netbeans.org/project_downloads/samples/Samples/Java%20Web/ifpwafcad.sql) и сохраните его в месте на вашем компьютере. Этот скрипт создает две таблицы, похожие на то, что вы только что создали выше ( `Советник` и `Субъект` ), и сразу же заполняет их данными.

Поскольку сценарий перезаписывает эти таблицы, если они уже существуют, удалите таблицы `Советника` и `Тема,` чтобы стало очевидно, что при запуске скрипта создаются новые таблицы. Чтобы удалить таблицы:

1. Щелкните правой кнопкой мыши узлы таблицы `советника` и `темы` в проводнике базы данных и выберите «Удалить».
2. Нажмите «Да» в диалоговом окне «Подтверждение удаления объекта». Обратите внимание, что в диалоговом окне перечислены таблицы, которые будут удалены.

Когда вы нажимаете «Да» в диалоговом окне «Подтверждение удаления объекта», узлы таблицы автоматически удаляются из Проводника базы данных.

Чтобы запустить SQL-скрипт в `MyNewDatabase` :

1. Выберите «Файл»> «Открыть файл» в главном меню среды IDE. В обозревателе файлов перейдите в папку, в которой вы ранее сохранили `ifpwafcad.sql,` и нажмите «Открыть». Скрипт автоматически открывается в редакторе SQL.

2. Убедитесь, что ваше соединение с `MyNewDatabase` выбрано в раскрывающемся списке «Соединение» на панели инструментов в верхней части редактора.

   ​

3. Нажмите кнопку «Запустить SQL» ( ![Запустить кнопку SQL](https://netbeans.org/images_www/articles/73/ide/mysql/run-sql-button.png)) на панели задач SQL Editor. Сценарий выполняется против выбранной базы данных, и любая обратная связь создается в окне «Вывод».

4. Чтобы проверить изменения, щелкните правой кнопкой мыши узел подключения `MyNewDatabase` в окне Runtime и выберите «Обновить». Параметр Refresh обновляет компонент пользовательского интерфейса Database Explorer до текущего состояния указанной базы данных. Обратите внимание, что две новые таблицы из сценария SQL теперь отображаются в виде табличных узлов в `MyNewDatabase` в Database Explorer.

5. Выберите «Просмотр данных» в меню правой кнопки мыши выбранного узла таблицы, чтобы просмотреть данные, содержащиеся в новых таблицах. Таким образом, вы можете сравнить табличные данные с данными, содержащимися в сценарии SQL, чтобы убедиться, что они совпадают.

[Отправьте нам свою обратную связь](https://netbeans.org/about/contact_form.html?to=3&subject=Feedback:%20Connecting%20to%20a%20MySQL%20Database)

## Смотрите также

На этом заканчивается руководство по подключению к базе данных MySQL. В этом документе показано, как настроить MySQL на вашем компьютере и настроить соединение с сервером базы данных из среды IDE NetBeans. В нем также описано, как работать с MySQL в среде Database Explorer, создавая новые экземпляры и таблицы базы данных, заполняя таблицы данными и запуская SQL-запросы.

Для связанных и расширенных руководств см. Следующие ресурсы:

- [Создание простого веб-приложения с использованием базы данных MySQL](https://netbeans.org/kb/docs/web/mysql-webapp.html) . Дополнительный учебник, демонстрирующий, как создать простое двухуровневое веб-приложение в среде IDE с использованием только что созданной базы данных MySQL.