## CENTOS
### CentOS: Install Packages Via yum Command Using DVD / CD as Repo

vi **/etc/yum.repos.d/CentOS-Media.repo**
```
enabled=1
```
To only use the DVDmedia repo, do this:
```
yum --disablerepo=\* --enablerepo=c5-media install pacakge-name
```

