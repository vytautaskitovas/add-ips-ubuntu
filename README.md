# Add IP Addresses Range to Ubuntu

This is a simple script to quickly assign IPv4 IP addresses ranges to specific interface on Ubuntu system. You can assign multiple ranges at once, even if it is /22 or bigger subnet. The scripts adds ranges to network interface and, also, commands to /etc/rc.local file so network interface would be updated after server restart.

## How to Use

You can run this script remotely on any Ubuntu based Linux machine using following command:

```bash
bash <(curl -s -L https://raw.githubusercontent.com/vytautaskitovas/data/master/ubuntuaddip.sh)
```

If you want to run this script locally, use these commands:
```
wget https://raw.githubusercontent.com/vytautaskitovas/data/master/ubuntuaddip.sh && chmod +x ubuntuaddip.sh
./ubuntuaddip.sh
```

**Please follow these rules when you want to add IPs:**
- At first scripts shows you current network interface;
- Write or paste all new ranges in a list format(e.g. 191.101.0.0/25) and press ctrl+d;
- The script will ask to enter network interface;
- IP addresses will be added to network interface and to /etc/rc.local file.
