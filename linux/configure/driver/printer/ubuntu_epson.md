# Download


`https://download.ebz.epson.net/dsc/search/01/search/?OSC=LX`



iscan-bundle-*.x64.deb.tar.gz
# Install
cd ~/Downloads
tar -xvf iscan-bundle-*.tar.gz
cd iscan-bundle-*

sudo dpkg -i *.deb
sudo apt -f install
# Fix permissions
sudo usermod -aG scanner $USER
sudo usermod -aG lp $USER

👉 Log out and back in (or reboot)

# Test scanner (USB connected)
scanimage -L

Expected result:

device `epkowa:usb:...' is a Epson scanner
# Scan

Use:

simple-scan

(or the default “Document Scanner” app)

# Notes
Works best via USB
Requires Epson’s proprietary driver (included in the bundle)
If it doesn’t detect the scanner, tell me the output of scanimage -L
