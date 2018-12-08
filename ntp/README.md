# Playbook pour configurer le service ntpd
ce playbook permet :

-  installer le service ntpd
-  modifier ntp.conf a partir d'un template qui utilise des serveurs ntp europeen
-  arreter le service ntp pour le synchroniser avec la machine manager (centos0)
-  enabler et demarrer le service ntp

# Utilisation

sudo ansible-playbook -i hosts ntp.yaml -k -K -s


## Verifications
sudo date -R
sudo ntpq -p

## Commandes utiles  
sudo systemctl status ntpd
sudo systemctl enable ntpd
sudo systemctl start ntpd

## Resynchro manuelle sur centos0
sudo systemctl stop ntpd
sudo ntpdate 0.pool.ntp.org
sudo systemctl start ntpd


# Sources Web
sources utilisées : 
- https://mdschreier.com/2016/05/13/setting-up-ntp-via-ansible-in-my-private-lab/
- https://www.it-connect.fr/modifier-lheure-et-la-date-sous-linux-avec-la-commande-date%EF%BB%BF/
- https://www.tecmint.com/install-ntp-server-in-centos/
- https://www.pool.ntp.org/zone/fr


# Divers : aspects connexes : 
- cle ssh : https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/
- copie cle ssh : https://www.ssh.com/ssh/copy-id
- centos hostname : https://support.rackspace.com/how-to/centos-hostname-change/
- centos repo : https://blog.microlinux.fr/yum-config/, http://www.mgroup.fr/index.php?pages/centos_depots_tiers, https://fedoraproject.org/wiki/EPEL
- markdown : https://dillinger.io/

raphael
