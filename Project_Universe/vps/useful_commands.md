# Useful Debian & Project Commands

## Debian Package Management
sudo apt-get update --- Updates package lists.
sudo apt-get upgrade --- Upgrades installed packages.
sudo apt-get install package --- Installs a package.

## System Services
sudo systemctl status redis-server --- Check Redis status.
sudo systemctl start redis-server --- Start Redis manually.
sudo systemctl stop redis-server --- Stop Redis.
sudo systemctl enable redis-server --- Enable Redis on startup.

## Networking & Ports
sudo lsof -i :4000 --- Check what’s using port 4000.
sudo netstat -tulpn | grep 4000 --- Another way to see which process uses port 4000.
sudo kill -9 PID --- Kill a process by PID.

## Nginx
sudo nginx -t --- Test Nginx config syntax.
sudo systemctl reload nginx --- Reload Nginx after changes.
sudo systemctl restart nginx --- Restart Nginx service.

## PM2 (Node Process Manager)
pm2 start server.js --name shaostoul-chat --- Start the chat service.
pm2 status --- Check running processes.
pm2 logs chat --- Tail logs for the app.
pm2 restart chat --- Restart the app.
pm2 stop chat --- Stop the app.
pm2 delete chat --- Remove from PM2 list.
pm2 save --- Save current process list for auto-start on reboot.

## Node & NVM
nvm install 20 --- Install Node 20.x (example).
nvm use 20 --- Switch to Node 20.
node -v --- Check Node version.