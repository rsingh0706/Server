### FTP Server overview

A computer program that allows users to securely transfer files over the internet. FTP servers use a client-server model. 

### Install vsftpd on Ubuntu

1. Update Package List: Before installing any package, it's a good idea to update your package list.

```bash
sudo apt update
```

2. Install vsftpd: Use the following command to install the vsftpd server.

```bash
sudo apt install vsftpd
```

3. Start and Enable vsftpd: After installation, you can start the FTP service and ensure it starts automatically on boot.

```bash
sudo systemctl start vsftpd
sudo systemctl enable vsftpd
```

4. Check Status of vsftpd: You can check if the FTP server is running with this command:

```bash
sudo systemctl status vsftpd
```

### Configuration of vsftpd

```bash
write_enable=YES/download file(put) >> NO/not download file
```

1. Install lftp:

```bash
sudo apt update
sudo apt install lftp
```

2. Connect to an FTP/SFTP server:

```bash
lftp user@ip
```

3. Transfer Files:
   Once connected, you can use commands like ls, cd, get, and put to navigate and transfer files.

4. Exit:
   Use the exit command or Ctrl+D to disconnect from the server.




