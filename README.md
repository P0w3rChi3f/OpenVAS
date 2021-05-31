# Notes taken while learnining OpenVAS

https://www.kali.org/blog/configuring-and-tuning-openvas-in-kali-linux/

## Steps to install OpenVAS on Kali

1. Make sure you are up to date  
    `sudo apt update -y`  
    `sudo apt upgrade -y`  
2. Install OpenVas  
    `sudo apt install openvas`
    `sudo gvm-setup`
    `sudd systemctl start redis-server`
    `sudo gvm-start`
    
    sudo runuser -u _gvm -- greenbone-nvt-sync
    sudo runuser -u _gvm -- greenbone-certdata-sync
    sudo runuser -u _gvm -- greenbone-scapdata-sync

    sudo greenbone-scapdata-sync
    sudo runuser -u _gvm -- greenbone-nvt-sync --refresh
    sudo 

## Steps to make WebUI avalable to network

1. `cd /lib/systemd/system`  
2. `vi greenbone-security-assistant.service`  
3. Change `127.0.0.1` to `0.0.0.0`
4. Change Admin password `sudo gvmd --user=admin --new-password=PassWord12#$34`
