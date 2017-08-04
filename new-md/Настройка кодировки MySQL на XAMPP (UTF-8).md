[![xampp control panel](https://zooks.ru/wp-content/uploads/2014/06/xampp_control_panel.png)](https://zooks.ru/web/189)

# [Настройка кодировки MySQL на XAMPP (UTF-8)](https://zooks.ru/web/189)

[01.06.2014](https://zooks.ru/web/189) / [ZOOKS](https://zooks.ru/web/author/zooks) / [2 COMMENTS](https://zooks.ru/web/189#comments)

Некоторые умельцы используют Денвер для тестирования сайта. Я думал, что эта косая сборка уже давно умерла.

Каюсь, я и сам использовал ее лет 10 назад. Но было очень неудобно, косо, глючно. Сразу же решил нормально поставить веб-сервер Apache + PHP + MySQL, оставив от Denwer лишь заглушку на Sendmail.
В установке и настройке связки нет ничего сложного, но натыкаешься на кучу подводных камней при первоначальном конфигурировании.

В наши дни сверхскоростей на эти поиски совершенно нет времени. Поэтому легче поставить готовую сборку и плясать уже от нее. Перепробовав множество решений, я рекомендую [XAMPP](https://www.apachefriends.org/).

И первая проблема, с которой сталкиваешься после установки XAMPP — это кодировка.
В сети есть хорошая инструкция от Sergey Danielyan: [Корректная настройка MySQL для работы с UTF8](http://gahcep.github.io/blog/2013/01/05/mysql-utf8/). Рекомендую почитать для понимания что такое charset и что такое collation. Здесь же опишу лишь алгоритм действий.

Кодировка MySQL настраивается в файле *my.ini* (в панели управления XAMPP: *Config > my.ini*)

В случае XAMPP директивы, описанные в вышеуказаной статье, можно сократить:

Перезапускаем службу. Заходим в консоль MySQL (в XAMPP: *Shell > mysql -uroot -p*), даем команды:

Как видим, теперь выставлена кодировка utf8 и сопоставление utf8_general_ci, чего мы и добивались.

```
+--------------------------+---------------------------------+
| Variable_name            | Value                           |
+--------------------------+---------------------------------+
| character_set_client     | utf8                            |
| character_set_connection | utf8                            |
| character_set_database   | utf8                            |
| character_set_filesystem | binary                          |
| character_set_results    | utf8                            |
| character_set_server     | utf8                            |
| character_set_system     | utf8                            |
| character_sets_dir       | D:\server\mysql\share\charsets\ |
+--------------------------+---------------------------------+

+----------------------+-----------------+
| Variable_name        | Value           |
+----------------------+-----------------+
| collation_connection | utf8_general_ci |
| collation_database   | utf8_general_ci |
| collation_server     | utf8_general_ci |
+----------------------+-----------------+

```

Лепота.
[![XAMPP MySQL charset](http://zooks.ru/wp-content/uploads/2014/06/xampp_mysql_charset.png)](http://zooks.ru/wp-content/uploads/2014/06/xampp_mysql_charset.png)

Categories: [DB](https://zooks.ru/web/category/web/db), [Uncategorized](https://zooks.ru/web/category/uncategorized)

 

Tags: [Apache](https://zooks.ru/web/tag/apache), [charset](https://zooks.ru/web/tag/charset), [MySQL](https://zooks.ru/web/tag/mysql), [PHP](https://zooks.ru/web/tag/php), [XAMPP](https://zooks.ru/web/tag/xampp), [кодировка](https://zooks.ru/web/tag/%d0%ba%d0%be%d0%b4%d0%b8%d1%80%d0%be%d0%b2%d0%ba%d0%b0)