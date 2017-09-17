# net-config
Config for iiab-server

cd ~/

git clone https://github.com/germanrs/net-config.git

cd ~/net-config

cp ~/net-config/dhcpd-iiab.conf.j2-g /opt/iiab/iiab/roles/network/templates/dhcp/

cp ~/net-config/iiab-gen-iptables-g /opt/iiab/iiab/roles/network/templates/gateway/

cp ~/net-config/named-iiab.conf.j2-g /opt/iiab/iiab/roles/network/templates/named/
