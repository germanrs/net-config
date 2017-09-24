# net-config
Config for iiab-server

## Clone
cd ~/

git clone https://github.com/germanrs/net-config.git

## Copy
cd ~/net-config

cp ~/net-config/dhcpd-iiab.conf.j2-g /opt/iiab/iiab/roles/network/templates/dhcp/

cp ~/net-config/iiab-gen-iptables-g /opt/iiab/iiab/roles/network/templates/gateway/

cp ~/net-config/named-iiab.conf.j2-g /opt/iiab/iiab/roles/network/templates/named/

## Modify 
vim /opt/iiab/iiab/roles/network/tasks/dhcpd.yml

   { src: 'dhcp/dhcpd-iiab.conf.j2', dest: '/etc/dhcpd-iiab.conf', mode: '0644' }
   { src: 'dhcp/dhcpd-iiab.conf.j2-g', dest: '/etc/dhcpd-iiab.conf', mode: '0644' }

vim /opt/iiab/iiab/roles/network/tasks/named.yml

   { src: 'named/named-iiab.conf.j2', dest: '/etc/named-iiab.conf', owner: "root" , mode: '0644' }
   { src: 'named/named-iiab.conf.j2-g', dest: '/etc/named-iiab.conf', owner: "root" , mode: '0644' }

vim /opt/iiab/iiab/roles/network/tasks/enable_services.yml

   { 0: 'gateway/iiab-gen-iptables', 1: '/usr/bin/iiab-gen-iptables' }
   { 0: 'gateway/iiab-gen-iptables-g', 1: '/usr/bin/iiab-gen-iptables' } 

## Apply
cd /opt/iiab/iiab/

./runansible
