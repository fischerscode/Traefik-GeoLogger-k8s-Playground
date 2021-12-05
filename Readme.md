**NOT PRODUCTION READY**

`< /dev/urandom tr -dc _A-Z-a-z-0-9 | head -c${1:-1048577} >> /var/log/access.log`