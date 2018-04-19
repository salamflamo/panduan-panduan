## untuk web-server , simpan di `/usr/local/bin`
```
#!/bin/bash
ip="$(ifconfig wlo1 | grep 'inet addr' | cut -d ':' -f 2 | cut -d ' ' -f 1)"
php -S $ip:$@
```

## untuk web-local, simpan di `/usr/local/bin`
```
#!/bin/bash
php -S localhost:$@
```
