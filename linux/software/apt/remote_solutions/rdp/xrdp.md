xrdp nachinstallieren / einrichten

sudo apt update && sudo apt upgrade -y

sudo apt install xrdp -y

sudo systemctl enable xrdp

sudo nano /etc/xrdp/startwm.sh
ALLES unterhalb von #!/bin/sh auskommentieren oder löschen
Nur DAS hier drin lassen:
#!/bin/sh 
unset DBUS_SESSION_BUS_ADDRESS 
unset XDG_RUNTIME_DIR 
exec /usr/bin/startxfce4

rm -f ~/.xsession ~/.Xauthority
echo "startxfce4" > ~/.xsession
chmod +x ~/.xsession

sudo systemctl restart xrdp
sudo systemctl restart xrdp-sesman
sudo systemctl restart lightdm || sudo systemctl restart gdm3

systemctl status xrdp

Firewall nicht vergessen!

Session: Xorg
Farbtiefe: 16-bit
Auflösung: max. 1280×800
