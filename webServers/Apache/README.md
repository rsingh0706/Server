### overview Apache

Apache is a cross-platform server software that runs on Unix, Linux, Windows, and macOS. It is capable of serving both static and dynamic content and can be configured to handle different protocols, such as HTTP, HTTPS, and FTP.


1. Basic Installation On Ubuntu/Debian:

```bash
sudo apt update
sudo apt install apache2 -y
```

2. Verify Installation Check if Apache is running:

```bash
sudo systemctl status apache2    
sudo systemctl status httpd     
```

3. Basic Configuration

```bash
/etc/apache2/apache2.conf
```


1. Stop the Apache Service 
   Before removing Apache, stop its service to ensure it’s not running:

```bash
sudo systemctl stop apache2
```

2. Remove Only the Apache Package:
   This will uninstall the Apache2 package but keep the configuration files and logs.

```bash
sudo apt remove apache2
```

3. Remove Apache Along with Configuration Files
   This will completely remove Apache, including its configuration files.

```bash
sudo apt purge apache2
```

4. Remove Unused Dependencies
   After uninstalling Apache, you might have unused dependencies that were installed with it. Clean them up with:

```bash
sudo apt autoremove
```

5. Delete Remaining Apache Files (Optional)
   If you want to remove all logs, configuration files, and other residual files, you can manually delete them:

```bash
sudo rm -rf /etc/apache2
sudo rm -rf /var/www/html
sudo rm -rf /var/log/apache2
```

6. Verify Apache Removal

```bash
apache2 -v
```


 





