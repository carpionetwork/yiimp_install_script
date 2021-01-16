# Yiimp_install_script 
* updated January, 2021
* v0.3 

***********************************

## Install script for yiimp on Ubuntu Server 16.04, 18.04, 20.*

USE THIS SCRIPT ON FRESH INSTALL UBUNTU Server 16.04, 18.04, 20.*

Connect on your VPS =>
- apt update
- apt upgrade
- reboot
- adduser pool ((or username of your choice))
- adduser pool sudo
- su - pool
- sudo apt -y install git
- cd /opt ((or directory of your choice))
- git clone https://github.com/carpionetwork/yiimp_install_script.git
- cd yiimp_install_script/
- bash install.sh ((do not run the script as root or sudo))
- At the end, you MUST REBOOT to finalize installation...

Web frontend:
* Go http://xxx.xxx.xxx.xxx
* https://xxx.xxx.xxx.xxx (if you have chosen LetsEncrypt SSL).

Admin Panel
* Go http://xxx.xxx.xxx.xxx/AdminPanel
* https://xxx.xxx.xxx.xxx/AdminPanel 


###### If you are issue after installation (nginx,mariadb... not found), use this script : bash install-debug.sh (watch the log during installation)


###### :bangbang: **Kudaraidee Install Script :**
- Instead Tpruvot's Yiimp, you can use the Kudaraidee's Repo Yiimp : git clone -b Kudaraidee https://github.com/Kudaraidee/yiimp.git
- It's an updated Yiimp, with more algo, some fix....

###### :bangbang: **YOU MUST UPDATE THE FOLLOWING FILES :**
- **/var/web/serverconfig.php :** update this file to include your public ip (line = YAAMP_ADMIN_IP) to access the admin panel (Put your PERSONNAL IP, NOT IP of your VPS). update with public keys from exchanges. update with other information specific to your server..
- **/etc/yiimp/keys.php :** update with secrect keys from the exchanges (not mandatory)
- **If you want change 'AdminPanel' to access Panel Admin :** Edit this file "/var/web/yaamp/modules/site/SiteController.php" and Line 11 => change 'AdminPanel'


###### :bangbang: **IMPORTANT** : 

- The configuration of yiimp and coin require a minimum of knowledge in linux
- Your mysql information (login/Password) is saved in **~/.my.cnf**

***********************************

###### This script has an interactive beginning and will ask for the following information :

- Server Name (no http:// or www !!!!! Example : crypto.com OR pool.crypto.com OR 80.41.52.63)
- Are you using a subdomain (mypoolx11.crypto.com)
- Enter support email
- Set stratum to AutoExchange
- Your Public IP for admin access (Put your PERSONNAL IP, NOT IP of your VPS)
- Install Fail2ban
- Install UFW and configure ports
- Install LetsEncrypt SSL

***********************************

**This install script will get you 95% ready to go with yiimp. There are a few things you need to do after the main install is finished.**

While I did add some server security to the script, it is every server owners responsibility to fully secure their own servers. After the installation you will still need to customize your serverconfig.php file to your liking, add your API keys, and build/add your coins to the control panel. 

There will be several wallets already in yiimp. These have nothing to do with the installation script and are from the database import from the yiimp github. 

If you need further assistance we have a small but growing discord channel at https://discord.gg/zcCXjkQ

If this helped you or you feel giving please donate : 
- BTC Donation : 1C1hnjk3WhuAvUN6Ny6LTxPD3rwSZwapW7
- BCH Donation : 1PqjApUdjwU9k4v1RDWf6XveARyEXaiGUz
- ETH Donation : 0xc23E6902fF8Cd8878EDADE18Dc49B3505395F0a1

***********************************

Site : https://www.velezcarpio.com

Discord : https://discord.gg/zcCXjkQ

TUTO Youtube (16.04 / 18.04 - Without SSL) : https://www.youtube.com/watch?v=qE0rhfJ1g2k

Official Yiimp (used in this script for Yiimp Installation): https://github.com/tpruvot/yiimp

Original Yiimp Installer : https://github.com/cryptopool-builders/multipool_original_yiimp_installer
