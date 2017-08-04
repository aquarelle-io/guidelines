Песочница

[ОЖИДАЮТ ПРИГЛАШЕНИЕ](https://habrahabr.ru/sandbox/)[ПОЛУЧИЛИ ПРИГЛАШЕНИЕ](https://habrahabr.ru/sandbox/invited/)[МОИ ПУБЛИКАЦИИ](https://habrahabr.ru/sandbox/my/)

21 марта 2014 в 21:12

# [Разработка](https://habrahabr.ru/flows/develop/) → XAMPP — настройка виртуального сервера

[Разработка веб-сайтов](https://habrahabr.ru/hub/webdev/)*

![image](http://blog.eukhost.com/wp-content/uploads/2011/05/XAMPP_logo.png)

скачать XAMPP

#### **XAMPP ver. 1.8.3-3 for Mac OS X ver. 10.9.2**

##### Первоначальная настройка

 

localhost

1. ​

 

 

daemon

 

 

username

 

 

```
171      #running httpd, as with most system services. 
172      # 
173      User daemon 
174      Group daemon 
175  </IfModule> 

```

 

username

 

```
171      #running httpd, as with most system services. 
172      # 
173      User username
174      Group daemon 
175  </IfModule>  

```

- Include etc/extra/httpd-vhosts.conf

```
487    #Virtual hosts
488    #Include etc/extra/httpd-vhosts.conf

```

```
487    #Virtual hosts                  
488    Include etc/extra/httpd-vhosts.conf 

```

2.

 

 

```
#localhost 
<VirtualHost *:80> 
    ServerName localhost 
    DocumentRoot "/Applications/XAMPP/xamppfiles/htdocs" 
    <Directory "/Applications/XAMPP/xamppfiles/htdocs"> 
        Options Indexes FollowSymLinks Includes execCGI 
        AllowOverride All 
        Allow From All 
        Order Allow,Deny 
    </Directory> 
</VirtualHost> 

```

 

```
#My custom host 
<VirtualHost *:80> 
    ServerName site.local 
    DocumentRoot "/Users/username/folder/site.local" 
    <Directory "/Users/username/folder/site.local"> 
        Options Indexes FollowSymLinks Includes ExecCGI 
        AllowOverride All 
        Require all granted 
    </Directory> 
    ErrorLog "logs/site.local-error_log" 
</VirtualHost> 

```

sudo /Applications/TextEdit.app/Contents/MacOS/TextEdit /etc/hosts

 

```
#XAMPP    VirtualHost  
127.0.0.1        site.local 

```

 

localhost

 

 

 

site.local

 

 

xampp, mac os x, localhost