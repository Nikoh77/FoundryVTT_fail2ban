# FoundryVTT_fail2ban
Just the fail2ban filter for Foundry Virtual Tabletop

## To add/append to jail.local on the fail2ban root dir (replacing where there are ***):
[***JailName***]\
enabled = true\
logpath = /***path2log***\
port = http,https\
filter = ***filterFileName***\
bantime  = 1h\
# Uncomment one of the two lines below according to your needs
#banaction = ssh-iptables[remote-host=***user***@***proxyIP***, type=multiport]\
#banaction = ssh-iptables-ipset[remote-host=***user***@***proxyIP***, type=multiport, blocktype=DROP]\

## On the proxy you must:
1) create a user with name as you want, this user must be part of the users e.g. group (100)\
2) give rights to iptables and/or bins like:\
chgrp users /usr/sbin/iptables (or ipset)\
chmod u+rxs /usr/sbin/iptables (o ipset)\
so user above can call needed commands as root...\
3) enable ssh connection with key (without asking password) from fail2ban PC to proxy PC with user above (ssh user@proxyIP)\
