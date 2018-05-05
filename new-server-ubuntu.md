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

- `sudo apt-get install php7.0 libapache2-mod-php7.0`

- `sudo apt-cache search php7.0`

- `sudo apt install libapache2-mod-php7.0 php-all-dev php7.0 php7.0-cgi php7.0-cli php7.0-common php7.0-curl php7.0-dev php7.0-gd php7.0-gmp php7.0-json php7.0-ldap php7.0-mysql php7.0-odbc php7.0-opcache php7.0-pgsql php7.0-pspell php7.0-readline php7.0-recode php7.0-sqlite3 php7.0-tidy php7.0-xml php7.0-xmlrpc libphp7.0-embed php7.0-bcmath php7.0-bz2 php7.0-enchant php7.0-fpm php7.0-imap php7.0-interbase php7.0-intl php7.0-mbstring php7.0-mcrypt php7.0-phpdbg php7.0-soap php7.0-sybase php7.0-xsl php7.0-zip php7.0-dba`

