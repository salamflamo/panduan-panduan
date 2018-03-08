# Panduan untuk membuat pub key untuk ssh

- membuat ssh key private dan public `ssh-keygen -t rsa`

- mencopy pub key ke server `ssh-copy-id -p [port_ssh] user@server`

- disable password login alias hanya bisa diakses menggunakan key buka `sudo nano /etc/ssh/sshd_config`

- cari bari `PasswordAuthentication yes` ganti `yes` menjadi `no`

- simpan dan restart `sudo service ssh restart`

- sekarang akses `ssh-copy-id -p [port_ssh] user@server`
