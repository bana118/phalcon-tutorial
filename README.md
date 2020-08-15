# phalcon-tutorial
/usr/local/etc/php/php.ini-development

# How to get started
/etc/apache2/apache2.confの以下の2箇所を編集

```
<Directory />
    Options FollowSymLinks
    AllowOverride All # None -> All
    Require all granted
</Directory>
```

```
<Directory /workspace/phalcon-tutorial/store> # /var/www -> /workspace/phalcon-tutorial
    Options FollowSymLinks
    AllowOverride All # None -> All
    Require all granted
</Directory>
```

/etc/apache2/sites-available/000-default.conf を編集

```
Documentroot /workspace/phalcon-tutorial/store # /var/www/html -> workspace/phalcon-tutorial/store
```

以下のコマンドを実行

```
a2enmod rewrite
apache2 service restart
```

http://localhost にアクセスすると以下のように表示される

![phalcon](https://user-images.githubusercontent.com/43720583/90316256-f72a8b80-df5b-11ea-89a7-64f8f93ff7a6.png)
