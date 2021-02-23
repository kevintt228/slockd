
# How to Install slockd

```
cd /usr/local
git clone https://github.com/kevintt228/slockd.git
ln -s /usr/local/slockd/slockd-init /etc/init.d/slockd
chkconfig --add slockd
if [ ! -d /var/run/slockd ]; then mkdir /var/run/slockd; fi
chown nobody.nobody /var/run/slockd -R
service slockd restart

```
# How to fix CentOS 6 EOL
```
rpm -e epel-release
cat <<-'EOF' > /etc/yum.repos.d/CentOS-Base.repo
[C6.10-base]
name=CentOS-6.10 - Base
baseurl=http://vault.centos.org/6.10/os/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-6
enabled=1
metadata_expire=never

[C6.10-updates]
name=CentOS-6.10 - Updates
baseurl=http://vault.centos.org/6.10/updates/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-6
enabled=1
metadata_expire=never

[C6.10-extras]
name=CentOS-6.10 - Extras
baseurl=http://vault.centos.org/6.10/extras/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-6
enabled=1
metadata_expire=never

[C6.10-contrib]
name=CentOS-6.10 - Contrib
baseurl=http://vault.centos.org/6.10/contrib/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-6
enabled=0
metadata_expire=never

[C6.10-centosplus]
name=CentOS-6.10 - CentOSPlus
baseurl=http://vault.centos.org/6.10/centosplus/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-6
enabled=0
metadata_expire=never
EOF

#wget https://www.getpagespeed.com/files/centos6-eol.repo -O /etc/yum.repos.d/CentOS-Base.repo

yum update -y
yum install epel-release -y
yum update -y
```
# Add support SCL
```
yum install centos-release-scl -y
wget https://www.getpagespeed.com/files/centos6-scl-eol.repo -O /etc/yum.repos.d/CentOS-SCLo-scl.repo
wget https://www.getpagespeed.com/files/centos6-scl-rh-eol.repo -O /etc/yum.repos.d/CentOS-SCLo-scl-rh.repo
```