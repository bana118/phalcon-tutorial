# phalcon-tutorial
PHPフレームワーク[Phalcon](https://docs.phalcon.io/)のチュートリアル  
VSCodeの[Remote Container 拡張](https://code.visualstudio.com/docs/remote/containers)の使用を推奨します．

# Create MySQL table
MySQLでデータベースとテーブルを事前に作成する必要があります．  

1. MySQLの初期設定
    ```
    service mysql start
    mysql_secure_installation
    ```

2. MySQLでデータベース，テーブルの作成
    ```
    mysql -u root
    mysql> CREATE DATABASE tutorial;
    mysql> USE tutorial;
    mysql> source /workspaces/phalcon-tutorial/tutorial/sql/create_users_table.sql
    mysql> exit
    ```

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

