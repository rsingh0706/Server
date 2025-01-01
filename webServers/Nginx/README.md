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



