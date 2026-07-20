nmcli connection show
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.ignore-auto-dns yes
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.dns "1.1.1.1 9.9.9.9"
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.dns-priority -42
sudo nmcli connection down "FRITZ!Box 6670 LM"
sudo nmcli connection up "FRITZ!Box 6670 LM"
sudo systemctl restart systemd-resolved








