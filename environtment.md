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
