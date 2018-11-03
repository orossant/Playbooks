# Playbook pour configurer le service ntpd
ce playbook permet :

-  installer le service ntpd
-  modifier ntp.conf a partir d'un template qui utilise des serveurs ntp europeen
-  arrete le service ntp pour le synchroniser avec la machine manager (centos0)
-  enable et start le service ntp

# Utilisation

ansible-playbook -i hosts ntp.yaml -k -K -s


## Verifications
date -R
ntpq -p

## Commandes utiles  
systemctl status ntpd
systemctl enable ntpd
systemctl start ntpd

## Resynchro manuelle
systemctl stop ntpd
ntpdate 192.168.169.136


# Sources Web
sources utilisées : 
- https://mdschreier.com/2016/05/13/setting-up-ntp-via-ansible-in-my-private-lab/
- https://www.it-connect.fr/modifier-lheure-et-la-date-sous-linux-avec-la-commande-date%EF%BB%BF/
- https://www.tecmint.com/install-ntp-server-in-centos/
- https://www.pool.ntp.org/zone/fr


# Divers

aspects connexes : 
- cle ssh : https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/
- cpoie cle ssh : https://www.ssh.com/ssh/copy-id
- centos hostname : https://support.rackspace.com/how-to/centos-hostname-change/
- centos repo : https://blog.microlinux.fr/yum-config/, http://www.mgroup.fr/index.php?pages/centos_depots_tiers, https://fedoraproject.org/wiki/EPEL
- markdown : https://dillinger.io/


