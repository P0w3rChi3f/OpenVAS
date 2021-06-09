# Notes taken while learnining OpenVAS

## Terminology

1. NVT - Network Vunlerability Test. Scan Definitions
2. GVM - Greenbone Vunlerability Management
3. GSM - Greenbone Security Manager - Commercial Vulnerability Management
4. CPE - Common Platform Enumeration
5. Source Addtion - Open Source version of OpenVAS

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
    `sudo runuser -u _gvm -- openvas -u`
    `sudo runuser -u _gvm -- greenbone-feed-sync --type GVMD_DATA`  
    `sudo runuser -u _gvm -- greenbone-feed-sync --type SCAP`  
    `sudo runuser -u _gvm -- greenbone-feed-sync --type CERT`  
    * Other sync commads
        `sudo runuser -u _gvm -- greenbone-nvt-sync`  
        `sudo runuser -u _gvm -- greenbone-certdata-sync`
        `sudo runuser -u _gvm -- greenbone-scapdata-sync`

## Steps to make WebUI avalable to network

1. `cd /lib/systemd/system`  
2. `vi greenbone-security-assistant.service`  
3. Change `127.0.0.1` to `0.0.0.0`
4. Change Admin password `sudo gvmd --user=admin --new-password=PassWord12#$34`

## Update NVT's

## Add targets  

1. Several ways to add targets.
    * Configuration -> Targets
    * Scans -> Tasks

## Scan targets

## Filter example

1. CVE-2021 sort-reverse=created rows=20 first=1 - NTV Filter
2. CVE-2021-25275 - CVE - CVE Filter

## Create a Custom Security Policy

1. Clone a current policy
2. Edit the newly cloned policy to match your organization policy

## References

1. [Online Admin Manual](https://docs.greenbone.net/GSM-Manual/gos-6/en/introduction.html)
2. [Kali Documentation](https://tools.kali.org/vulnerability-analysis/openvas)  
3. [Kali Blog](https://www.kali.org/blog/configuring-and-tuning-openvas-in-kali-linux/)
4. [ICON Cheatsheet](./Icons-Job-Aid.pdf)
5. [PowerPoint Presentation](https://1drv.ms/p/s!AuVRl2Nl_6Ovn09qm9buUogKTbTH?e=1sBAPb)