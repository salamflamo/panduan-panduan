# Panduan untuk membuat user mysql baru dengan database yang sudah ditentukan dan membuat bisa diremote

- Remote server menggunakan `ssh`

- Edit file dengan menggunakan `nano /etc/mysql/mysql.conf.d/mysqld.cnf `

- Temukan `bind-address     = 127.0.0.1` kemudian depannya kasih `#` sehingga `#bind-address     = 127.0.0.1`

- Kemudian buat dibawahnya lagi `bind-address     = 0.0.0.0` agar dapat diakses melalui komputer mana saja yang konek dengan server

- Kemudian ctrl+x kemudian pilih Y kemudian enter
