# Firewall

```
// Install Firewall Service
sudo yum install firewalld
sudo systemctl start firewalld
sudo systemctl enable firewalld


// Configure Port
sudo firewall-cmd --permanent --zone=public --add-port=3306/tcp
sudo firewall-cmd --reload


```