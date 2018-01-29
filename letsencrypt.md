# Panduan untuk menggunakan letsencrypt ubuntu server 16.04

## Install

- Pertama remote VPS menggunakan `ssh` => `ssh -p 9008 user@vps.com` -p diunakan port, 9008 angka port

- Kemudian install `sudo add-apt-repository ppa:certbot/certbot`

- Update repo `sudo apt update` 

- Install letsencrypt `sudo apt-get install python-certbot-apache`

## Menggunakan 

- Pertama bikin file .conf untuk domain yg akan didaftarkan di `/etc/apache2/sites-available/web.conf`

- Kemudian edit file tadi menggunkan nano

- Edit bagian `ServerName sub.domain.com` menjadi domain yg akan didaftarkan

- Kemudian tambah `Redirect / https://meetingapp.salamflamo.xyz/` line bawah

- Jika sudah exit dan save

- kemudian aktifkan site `sudo a2ensite web.conf`

- Jika sudah reload `sudo service apache2 reload`

- Kemudian mulai `sudo certbot --authenticator standalone --installer apache --pre-hook "service apache2 stop" --post-hook "service apache2 start"` apache itu untuk webserver apache2, apache2 untuk nama service, jika nginx maka ganti nginx

- Enter maka akan muncul daftar domain, pilih domain yang akan didaftarkan disini `sub.domain.com` maka pilih itu

- Jika sudah biarkan proses selesai

- Kemudian akan membuat file .conf tetapi ada embel2 `-le-ssl.conf` menjadi `web-le-ssl.conf` edit file itu menggunakan nano

- Cari `Redirect / https://meetingapp.salamflamo.xyz/` kemudian beri tanda # untuk menonaktifkan `#Redirect / https://meetingapp.salamflamo.xyz/` jika sudah save

- Langkah terakhir reload apache2
