# Hapus valid password plugin yang menyusahkan

- Masuk ke mysql kamu `mysql -u root -p`

- Kemudian ketik perintah `uninstall plugin validate_password;` jika sudah `exit`

# Panduan untuk mengatasi sql mode

- Pertama buka setting mysql di `/etc/mysql/mysql.cnf` edit menggunakan `nano` dengan perintah `sudo nano /etc/mysql/mysql.cnf`

- Kemudian baris terakhir ditambahkan seperti ini

`[mysqld]
sql_mode=STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION`

- Kemudian save dan restart mysql `sudo service mysql restart`

- Selesai
