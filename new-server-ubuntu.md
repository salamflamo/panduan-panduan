# Panduan untuk server ubuntu baru

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
