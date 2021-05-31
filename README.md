# Notes taken while learnining OpenVAS

## Terminology

1. NVT - Network Vunlerability Test. Scan Definitions
2. GVM - Greenbone Vunlerability Management
3. GSM - Greenbone Security Manager - Commercial Vulnerability Management
4. Source Addtion - Open Source version of OpenVAS


## Steps to install OpenVAS on Kali

1. Make sure you are up to date  
    `sudo apt update -y`  
    `sudo apt upgrade -y`  
2. Install OpenVas  
    `sudo apt install openvas`
    `sudo gvm-setup`
    `sudo gvm-feed-update`
    `sudo systemctl start redis-server`
    `sudo gvm-start`
3. Troubleshooting/optional commands  
    `sudo runuser -u _gvm -- greenbone-nvt-sync`  
    `sudo runuser -u _gvm -- greenbone-certdata-sync`  
    `sudo runuser -u _gvm -- greenbone-scapdata-sync`  

## Steps to make WebUI avalable to network

1. `cd /lib/systemd/system`  
2. `vi greenbone-security-assistant.service`  
3. Change `127.0.0.1` to `0.0.0.0`
4. Change Admin password `sudo gvmd --user=admin --new-password=PassWord12#$34`

## Add targets  

1. 

## Scan targets

## Update NVT's

## References

1. [Online Admin Manual](https://docs.greenbone.net/GSM-Manual/gos-6/en/introduction.html)
2. [Kali Documentation](https://tools.kali.org/vulnerability-analysis/openvas)  
3. [Kali Blog](https://www.kali.org/blog/configuring-and-tuning-openvas-in-kali-linux/)