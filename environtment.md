# Setting my own environtment

## Setting blue light filter

- install redshift `sudo apt install redshift` dan `sudo apt-get install geoclue-2.0` 

- jika sudah `sudo cp /usr/share/applications/redshift.desktop /etc/xdg/autostart/`

- kemudian `sudo gedit /etc/xdg/autostart/redshift.desktop`

- ganti `Terminal=true` menjadi `Terminal=false` dan `NoDisplay=false` menjadi `NoDisplay=true`

## Editor dan tambahan

- install `atom` dan plugins seperti di drive

- install `gedit`

- install `git`

- install `chrome`

- install `wine` dan install `sql yog` **jangan _bajakan_**

- install `tmux` => `sudo apt install tmux` , cara menggunakan `ctrl+b "` horizontal , `ctrl+b %` vertical

- install `sshpass` cara menggunakan `sshpass -p 'password' ssh -p [port] -t user@host "command"`

## Install composer

- buka terminal dan ketik perintah dibawah satu persatu

- `php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"`

- `php -r "if (hash_file('SHA384', 'composer-setup.php') === '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"`

- `php composer-setup.php`

- `php -r "unlink('composer-setup.php');"`

- kemudian setelah selesai cek apakah ada file `composer.phar` atau tidak, ketik `ls | grep composer`

- jika masih gagal lihat situ [composer](https://getcomposer.org/download/)

- jika ada maka lanjutkan perintah `sudo cp composer.phar /usr/local/bin/composer`

- kemudian aktifkan `mode_rewrite` keti `sudo a2enmod rewrite && sudo service apache2 reload`

## Membuat vihost agar bisa symlink

- buka terminal kemudian `sudo nano /etc/apache2/sites-available/000-default.conf`

- kemudian tambahkan ini dibawah `DocumentRoot /var/www/html/`

```
<Directory /var/www/html/>
      Options Indexes FollowSymLinks
      AllowOverride All
      Require all granted
</Directory>
```
- kemudian save dan `sudo service apache2 reload`

## Membuat terminal lebih pendek

- buka terminal

- kemudian `sudo gedit ~/.bashrc`

- kemudian cari `PS1='${debian_chroot:+($debian_chroot)}\[\033[01;36m\]\u@\h\[\033[00m\] \[\033[01;37m\]\w \$\[\033[00m\] '`

- disitu terdapat huruf `w` kecil, ubah menjadi huruf `W` besar

- kemudian save , close dan buka lagi terminal

## Membuat executor projek berbasis php

- buka terminal kemudian `nano jalankan` ini nama file saya

- kemudian buatlah seperti ini

```
#!/bin/bash
php -S localhost:$@
```

- kemudian save dan ubah `chmod` `chmod 755 jalankan && chmod +x jalankan`

- agar dapat diakses global, pindah jalankan `sudo mv jalankan /usr/local/bin`

- untuk menjalankan ketik `jalankan [port]` di terminal, contoh `jalankan 9000` maka project php jalan di `localhost:9000`
