## Oracle linux v6

### Подключить ol6_software_collections

```
/etc/yum.repos.d
mv public-yum-ol6.repo  public-yum-ol6.repo.bak
wget http://yum.oracle.com/public-yum-ol6.repo
```


Отредактировать **public-yum-ol6.repo**

```
[ol6_software_collections]
name=Software Collection Library release 3.0 packages for Oracle Linux 6 (x86_64)
baseurl=https://yum.oracle.com/repo/OracleLinux/OL6/SoftwareCollections/x86_64/
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-oracle
gpgcheck=1
enabled=1  

```
