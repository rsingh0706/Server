### Niginx overview 
Nginx (pronounced "Engine-X") is a high-performance web server and reverse proxy server, known for its speed, scalability, and efficiency in handling modern web traffic. It is widely used for serving static content, load balancing, caching, and acting as a gateway for various applications.

1. Install Nginx

```bash
sudo apt update
sudo apt install nginx -y
```

2. Start and Enable Nginx

```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

3. Verify Installation

```bash
curl http://localhost
```


### Advanced Configuration

1. Nginx Directory Structure

```bash
Configuration: /etc/nginx/
Main config: /etc/nginx/nginx.conf
Sites-enabled: /etc/nginx/sites-enabled/ (Default config file)
Logs: /var/log/nginx/
Web Root: /var/www/html/
```

wil do advance configuration in nginx...


### To completely remove Nginx from an Ubuntu system, you can follow these steps:

1. Stop the Nginx Service

```bash
sudo systemctl stop nginx
```

2. Uninstall Nginx
   To remove Nginx and its associated packages, use:

```bash
sudo apt remove nginx nginx-common
```

3. If you want to remove Nginx along with its configuration files:

```bash
sudo apt purge nginx nginx-common
```

4. Remove Dependencies
   Remove any unneeded dependencies left after uninstalling Nginx:

```bash
sudo apt autoremove
```

5. Delete Nginx Configuration Files
   If any configuration files were not removed during the purge, delete them manually:

```bash
sudo rm -rf /etc/nginx
```

6. Remove Logs and Cache Delete Nginx logs and cached files:

```bash
sudo rm -rf /var/log/nginx
sudo rm -rf /var/cache/nginx
```

7. Verify Removal

```bash
nginx -v
```








