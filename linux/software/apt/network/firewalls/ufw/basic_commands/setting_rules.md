    To allow incoming traffic on a specific port: 
sudo ufw allow [port number]

    To allow incoming traffic on a specific port and protocol: 
sudo ufw allow [protocol] [port number]

    To deny incoming traffic on a specific port: 
sudo ufw deny [port number]

    To allow incoming traffic for a specific IP address: 
sudo ufw allow from [IP address]

    To deny incoming traffic for a specific IP address: 
sudo ufw deny from [IP address]


ufw allow out on <Networkinterface> to 1.1.1.1 proto udp port 53 comment ‘allow DNS on <Networkinterface>’
ufw allow out on <Networkinterface> to any proto tcp port 80 comment ‘allow HTTP on <Networkinterface>’
ufw allow out on <Networkinterface> to any proto tcp port 443 comment ‘allow HTTPS on <Networkinterface>’


ufw allow out on <interface> from <ip> to ip proto tcp port 9999
