Linux server1.shaostoul.com 5.10.0-9-amd64 #1 SMP Debian 5.10.70-1 (2021-09-30) x86_64

**List server.js service**
sudo lsof -i :4000

**Kill server.js service**
sudo kill -9 2283702

**PM method for resetting server**
pm2 stop shaostoul-chat
pm2 delete shaostoul-chat
pm2 start server.js --name chat
pm2 logs shaostoul-chat