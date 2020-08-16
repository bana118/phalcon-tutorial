# phalcon-tutorial
PHPフレームワーク[Phalcon](https://docs.phalcon.io/)のチュートリアル

# How to get started
Phalcon developer toolを使って開発用サーバーを起動

```
cd tutorial
phalcon serve
```

http://localhost:8000 にアクセス

# How to get started with apache
/etc/apache2/apache2.confの以下の2箇所を編集

```
<Directory />
    Options FollowSymLinks
    AllowOverride All # None -> All
    Require all granted
</Directory>
```

```
<Directory /workspaces/phalcon-tutorial/store> # /var/www -> /workspace/phalcon-tutorial
    Options FollowSymLinks
    AllowOverride All # None -> All
    Require all granted
</Directory>
```

/etc/apache2/sites-available/000-default.conf を編集

```
Documentroot /workspaces/phalcon-tutorial/store # /var/www/html -> /workspaces/phalcon-tutorial/tutorial
```

以下のコマンドを実行

```
a2enmod rewrite
service apache2 restart
```

http://localhost にアクセス

