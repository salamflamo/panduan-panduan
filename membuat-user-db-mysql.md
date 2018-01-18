# Membuat user mysql baru dengan database yang sudah ditentukan dan membuat bisa diremote

### Database allow remote access

- Remote server menggunakan `ssh`

- Edit file dengan menggunakan `nano /etc/mysql/mysql.conf.d/mysqld.cnf `

- Temukan `bind-address     = 127.0.0.1` kemudian depannya kasih `#` sehingga `#bind-address     = 127.0.0.1`

- Kemudian buat dibawahnya lagi `bind-address     = 0.0.0.0` agar dapat diakses melalui komputer mana saja yang konek dengan server

- Kemudian ctrl+x kemudian pilih Y kemudian enter

- Terakhir restart package `sudo service restart namapackage` namanya `apache2` , `mysql`


### Membuat database baru

- Buka mysql dengan `mysql -u root -p` ini apabila user root masih defaul, isi password nya

- Ada `mysql>` kemudian `CREATE DATABASE anubase CHARACTER SET utf8 COLLATE utf8_general_ci;`

- Buat user untuk localhost `create user 'anuu'@'localhost' identified by 'anuu';`

- Beri access privileges hanya untuk database anubase `grant all privileges on anubase.* to 'anuu'@'localhost';`

- Kemudian `create user 'anuu'@'%' identified by 'anuu';` tanda % untuk semua host dapat mengakses

- Kemudian `grant all privileges on anubase.* to 'anuu'@'%';` ini juga sama seperti diatas

- Kemudian terakhir `flush privileges;`

- Kemudian exit dan test menggunakan sql yog, mysql work branch dsb
