
# How to Install slockd

(```)
cd /usr/local
git clone https://github.com/kevintt228/slockd.git
ln -s /usr/local/slockd/slockd-init /etc/init.d/slockd
chkconfig --add slockd
service slockd restart
(```)
# How to fix CentOS 6 EOL
(```)
rpm -e epel-release
wget https://www.getpagespeed.com/files/centos6-eol.repo -O /etc/yum.repos.d/CentOS-Base.repo
yum install epel-release -y
yum update -y
(```)