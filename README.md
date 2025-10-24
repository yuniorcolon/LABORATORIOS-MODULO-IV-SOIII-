#!/bin/bash
sudo dnf install httpd
sudo systemctl start httpd
sudo systemctl status httpd
cd /var/www/
mkdir HolaMundo
chmod 755 HolaMundo
sudo chown apache:apache HolaMundo
sudo nano index.html
cd /etc/httpd/
cd conf.d
sudo nano HolaMundo.conf
cd /var/www/
mkdir materia
chmod 755 materia
cp HolaMundo materia
cd materia
sudo nano index.html
cd /etc/httpd/
cd conf
sudo nano httpd.conf
cd /etc/httpd/
cd conf.d
sudo nano materia.conf
sudo systemctl restart httpd
sudo dnf install cups
sudo dnf install epel-release
sudo dnf install cups-pdf
sudo systemctl start cups
sudo systemctl status cups
sudo firewall-cmd --permanent --add-service=ipp
sudo firewall-cmd --permanent --add-service=ipp-client
sudo firewall-cmd --reload
sudo systemctl restart cups
