# 📦 SCP Cheat Sheet (PowerShell / OpenSSH)

## ▶️ Basic Syntax
scp [options] <source> <destination>

---

## 🔑 Common Options

| Option | Description |
|--------|-------------|
| -r     | Recursive copy (directories) |
| -P     | Specify port (uppercase P!) |
| -i     | Identity file (private key) |
| -v     | Verbose output (debugging) |
| -C     | Enable compression |
| -q     | Quiet mode |
| -l     | Limit bandwidth (Kbit/s) |

---

## 📂 Local → Remote

Copy file:
scp file.txt user@host:/path/

Copy directory:
scp -r folder user@host:/path/

---

## 📥 Remote → Local

Copy file:
scp user@host:/path/file.txt .

Copy directory:
scp -r user@host:/path/folder .

---

## 🔁 Remote → Remote

scp user1@host1:/path/file user2@host2:/path/

---

## 🔐 Use SSH Key

scp -i C:\Keys\id_rsa file.txt user@host:/path/

---

## 🌐 Custom Port

scp -P 2222 file.txt user@host:/path/

---

## ⚡ Combine Options

scp -r -C -i C:\Keys\id_rsa -P 2222 folder user@host:/path/

---

## 🧠 Tips

- Requires OpenSSH client (included in modern Windows / PowerShell)
- Local paths: C:\folder\file.txt
- Remote paths: /home/user/file.txt
- Use quotes for spaces:
  scp "C:\My Files\file.txt" user@host:"/home/user/My Files/"

---

## ⚠️ Notes

- Uses SSH (port 22 by default)
- Permissions depend on remote system
- Firewall must allow SSH
- scp is still widely used but sometimes replaced by sftp or rsync

---

## ✅ Quick Examples

Upload file:
scp file.txt admin@192.168.1.10:/tmp/

Download file:
scp admin@192.168.1.10:/tmp/file.txt .

Upload folder with key + port:
scp -r -i C:\key.pem -P 2222 folder admin@host:/var/www/
