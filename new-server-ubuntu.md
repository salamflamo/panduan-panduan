# Panduan untuk server ubuntu baru

## Membuat user akses sudo baru

- Buat droplet di digital ocean dengan OS ubuntu dan pake $5/month jangan mahal-mahal

- Akses menggunakan ssh dan ganti password

- ketik `adduser username`

```
Set password prompts:
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully

User information prompts:
Changing the user information for username
Enter the new value, or press ENTER for the default
    Full Name []:
    Room Number []:
    Work Phone []:
    Home Phone []:
    Other []:
Is the information correct? [Y/n]
```

- kemudian `usermod -aG sudo username`

- jika sudah exit

## Menyiapkan depedencies yang dibutuhkan

### Install apache2

- `sudo apt install apache2`

- `sudo nano /etc/apache2/apache2.conf`

- tambah di baris terakhir `ServerName server_domain_or_IP`

- simpan kemudian `sudo service apache2 restart`

- `sudo ufw allow in "Apache Full"`

- setelah itu edit file `sudo nano /etc/apache2/mods-enabled/dir.conf`

- kemudian terlihat `DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm` pindahkan `index.php` di barisan paling depan

- jika sudah save dan `sudo service apache2 reload`

### Install mysql

- `sudo apt install mysql-server mysql-client`

- `mysql_secure_installation`

```
Enter password for user root : <= y
Change the password for root ? ((Press y|Y for Yes, any other key for No) : <= n
Remove anonymous users? (Press y|Y for Yes, any other key for No) : <= y
Disallow root login remotely? (Press y|Y for Yes, any other key for No) : <= n
Remove test database and access to it? (Press y|Y for Yes, any other key for No) : <= y
Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y <=
```
- buat user `root` dengan akses `%`
- buat `sql_mode` untuk menghapus `only_full_group_by`

### Install php
- `install python-software-properties`

- `sudo add-apt-repository ppa:ondrej/php`

#### Versi 7.0
- `sudo apt-get install php7.0 libapache2-mod-php7.0`

- `sudo apt-cache search php7.0` << cek yang bisa diinstall

- `sudo apt install libapache2-mod-php7.0 php-all-dev php7.0 php7.0-cgi php7.0-cli php7.0-common php7.0-curl php7.0-dev php7.0-gd php7.0-gmp php7.0-json php7.0-ldap php7.0-mysql php7.0-odbc php7.0-opcache php7.0-pgsql php7.0-pspell php7.0-readline php7.0-recode php7.0-sqlite3 php7.0-tidy php7.0-xml php7.0-xmlrpc libphp7.0-embed php7.0-bcmath php7.0-bz2 php7.0-enchant php7.0-fpm php7.0-imap php7.0-interbase php7.0-intl php7.0-mbstring php7.0-mcrypt php7.0-phpdbg php7.0-soap php7.0-sybase php7.0-xsl php7.0-zip php7.0-dba`

#### Versi 7.2

- `sudo apt get install php7.2`

- `sudo apt search php7.2`

- `sudo apt install libapache2-mod-php7.2 libphp7.2-embed php-all-dev php7.2 php7.2-bcmath php7.2-bz2 php7.2-cgi php7.2-cli php7.2-common php7.2-curl php7.2-dba php7.2-dev php7.2-enchant php7.2-fpm php7.2-gd php7.2-gmp php7.2-imap php7.2-interbase  php7.2-intl php7.2-json php7.2-ldap php7.2-mbstring php7.2-mysql php7.2-odbc php7.2-opcache php7.2-pgsql php7.2-phpdbg php7.2-pspell php7.2-readline php7.2-recode php7.2-soap php7.2-sqlite3 php7.2-sybase php7.2-tidy php7.2-xml php7.2-xmlrpc php7.2-xsl php7.2-zip` 

### Upgrade
- `sudo apt update && sudo apt upgrade`

### Pinda versi PHP
- `sudo update-alternatives --set php /usr/bin/php7.0` << disini bisa berdasarkan versi php

