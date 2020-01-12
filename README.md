# lightsail-iptv
IPTV for Plex DVR on Lightsail

## Create instance
Create AWS Lightsail instance via [AWS Lightsail CLI](https://docs.aws.amazon.com/cli/latest/reference/lightsail/index.html "AWS Lightsail CLI")
```
aws lightsail create-instances --instance-names "lightsail-iptv-eu-central-vm" --availability-zone eu-central-1a --blueprint-id centos_7_1805_01 --bundle-id medium_2_0 --user-data file://user-data.txt
```
You can find the script in `/var/lib/cloud/instance/user-data.txt` on the instance

## Configure instance
### Open ports
```
aws lightsail open-instance-public-ports --port-info fromPort=443,toPort=443,protocol=TCP --instance-name lightsail-iptv-eu-central-vm
aws lightsail open-instance-public-ports --port-info fromPort=32400,toPort=32400,protocol=TCP --instance-name lightsail-iptv-eu-central-vm
```
