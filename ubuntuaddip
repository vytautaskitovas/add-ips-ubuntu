#!/bin/bash

# Subnet calculator prips is being used.
ip a

dpkg -s prips 2>/dev/null >/dev/null || sudo apt-get -y install prips

echo "Enter subnets list and when done hit ctrl+d (e.g. 191.101.0.0/25):"

SUBNETS=$(cat)

for i in $SUBNETS; do
prips $i >> /tmp/subnetslist.txt
done

echo "Subnets list written to /tmp/subnetslist.txt, now enter interface name:"
read INTERFACE

for i in `cat /tmp/subnetslist.txt` ; do
echo "$i"
ip addr add $i/32 dev $INTERFACE 
echo "ip addr add $i/32 dev $INTERFACE" >> /etc/rc.local
done

sed -i '/exit 0/d' ./infile
echo "exit 0" >> /etc/rc.local

echo "Script completed, info written to /etc/rc.local so ips would be added automatically upon system boot, please check network interface:"
ip a
