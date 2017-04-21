# Let’s Encrypt получаем бесплатные SSL ключи

https://letsencrypt.org/getting-started/


##  Установка Certbot ACME client 

https://certbot.eff.org/

Выбираем платформу и OS, далее действуем по тексту.

Для CENTOS7 и nginx:

**sudo yum install epel-release**

**sudo yum install certbot


Для DEBIAN 8 и nginx:

Добавляем в **/etc/apt/sources.list**:

```
deb http://ftp.debian.org/debian jessie-backports main
```

**apt-get update**

**sudo apt-get install certbot -t jessie-backports**


## Второй этап
