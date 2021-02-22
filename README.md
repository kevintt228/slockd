cd /usr/local
git clone https://github.com/kevintt228/slockd.git
ln -s /usr/local/slockd/slockd-init /etc/init.d/slockd
chkconfig --add slockd
service slockd restart