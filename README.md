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

vim /opt/iiab/iiab/roles/network/tasks/named.yml

vim /opt/iiab/iiab/roles/network/tasks/enable_services.yml

## Apply
cd /opt/iiab/iiab/

./runansible
