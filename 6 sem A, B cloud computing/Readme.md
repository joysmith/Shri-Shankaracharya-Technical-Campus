## PART 1

1.  go to aws console, select asia-pacific mumbai region
1.  create ec2 instance: service -> compute -> ec2 instance
1.  select running instance
1.  select launch instance, then
1.  select ubuntu image as an OS as t2-micro (free one)
1.  create key-pair login .pem file or .ppk file, then launch server
1.  select "connect to server"
1.  select tab EC2 instant connect -> connect (to log in ubuntu server directly from browser)
1.  download & install putty [click me](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
1.
1.  open putty app, copy public ip from aws instance to "host name" ex: "ubuntu@51.20.191.33"
1.  open putty gen app to generate private .ppk file from .pem file
1.  under connection -> SSH -> auth -> credential -> .ppk (select private key file)
1.  In putty go to session and saved it with some name, then load it and open putty session to log in ubuntu server

### how to directly open session on browser without putty

1.  go to aws console and select any instance -> (look on above tab) connect -> (look below do scrolling)connect

## PART 2

How to use [request module ](https://www.npmjs.com/package/request) ?
<br>
<br>

# Project setup

1. update the ubuntu server

```
  sudo apt update
```

2. upgrade the ubuntu server

```
  sudo apt upgrade
```

3. Install apache2 server package

```
  sudo apt install apache2
```

4. How to test if the apache2 server is running or not

```
  sudo service apache2 status
```

# How to edit DNA A records in godaddy

1. Go to Godaddy dashboard and click on DNS

- <img src="image%20notes/1%20DNS.png" width="700">

2. Edit A record

- <img src="image%20notes/2%20edit%20A%20record.png" width="700">

# About apache2 package structure

1. Where do apache2 server live

```
  cd /etc/apache2/
  pwd
```

2. Where to find html file

```
  cd /var/www/html
  pwd
  ls -l
```

# Getting a project from git to ubuntu server

- <img src="image%20notes/3%20git%20project.png" width="700">

1. go to this location /var/www

```
  cd /var/www
  pwd
  ls
```

2. remove the html-directory

```
  sudo rm -r html/
  ls
```

3. copy the project link from git

```
  https://github.com/robertbunch/jquery-todo.git
```

4. run the cmd to copy project from git to ubuntu server

```
  sudo git clone https://github.com/robertbunch/jquery-todo.git html
```

5. Disection of cmd " sudo git clone https://github.com/robertbunch/jquery-todo.git html "

- sudo git clone https://github.com/robertbunch/jquery-todo.git 👉html
- the html there after the git link is telling create a html-directory
- and inside of that html-directory paste the project file

6. Optional:

- where is git binary located

```
  which git
```

- which git version is installed in ubuntu server

```
  git --version
```

# Generating HTTPS certificate and a VirtualHost

1. run the following cmds

```
  sudo snap install core; sudo snap refresh core
  sudo snap install --classic certbot
  sudo ln -s /snap/bin/certbot /usr/bin/certbot
```

2. go to this dir " /etc/apache2/sites-availabe "

```
  cd /etc/apache2/sites-availabe
```

3. create virtual host

```
  sudo nano joisland.com.conf
```

4. write these line in joisland.com.conf file

```
<VirtualHost *:80>
  ServerName joisland.com
  DocumentRoot /var/www/joisland
  <Directory "/var/www/joisland">
    allow from all
    AllowOverride All
    Order allow,deny
    Options +Indexes
  </Directory>
</VirtualHost>
```

- Exp:

```
++++  listening on port 80  ++++
<VirtualHost *:80>

++++ we are telling apache If someone shows up looking up for this url ++++
  ServerName joisland.com
  DocumentRoot /var/www/joisland

++++  I want apache u to look here in this directory  ++++
  <Directory "/var/www/joisland">

+++ The rest are apache cmd handle by apache +++
    allow from all
    AllowOverride All
    Order allow,deny
    Options +Indexes
  </Directory>
</VirtualHost>
```

5. go to this location " /var/www " then,

- " sudo mv html joisland "
- Exp: move all files inside html-dir to joisland-dir

```
  cd /var/www
  ls
  sudo mv html joisland
  ls
```

6. go to this dir " /etc/apache2/sites-availabe "

```
  cd /etc/apache2/sites-availabe
  ls
```

7. enabling the site

```
  sudo a2ensite joisland.com.conf
  sudo service apache2 reload
```

8. Add new inbound rule for https traffic in ubuntu aws

- <img src="image%20notes/6%20new%20inbound%20rule%20for%20https%20trafic.png" width="700">

9. run cmd for generating new virtual host

```

  sudo certbot --apache
                  OR
  sudo certbot --authenticator standalone --installer apache -d joisland.com --pre-hook "systemctl stop apache2" --post-hook "systemctl start apache2"
```

9.

# Notes

1. What is web server

- 1. Case: It means actual computer hardware in India
- 2. Case: A piece of software that sole job is to handle and manage http traffic
- 3. A system integrated lots of diff. networking piece moving

2. Ports conventions

- 1. port 80 for http traffic
- 2. port 20 for ssh traffic
- 3. port 443 for https traffic
- 4. Open network ports: can be use for any general purpose 8000, 3000, 8080, etc
