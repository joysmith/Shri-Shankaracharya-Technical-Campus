# Create Linux Instance - Using Putty to connect to Linux Instance, Implement Apache Web Server on Linux Instance

### PART 1

1.  Go to aws console, select asia-pacific mumbai region
1.  Create ec2 instance: service -> compute -> ec2 instance
1.  Select "running instance"
1.  Select "launch instance", then
1.  Select "ubuntu" image as an OS as t2-micro (free one)
1.  Create key-pair login ".pem" file or .ppk file, then launch server
1.  Select "connect to server"
1.  Download & install putty [click me](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
1.  Open putty app, copy public ip from aws instance to "host name" ex: "ubuntu@51.20.191.33"
1.  Open putty gen app to generate private .ppk file from .pem file
1.  In putty app, under connection -> SSH -> auth -> credential -> .ppk (select private key file)
1.  In putty go to session and saved it with some name, then load it and open putty session to log in to ubuntu server

#### how to directly open session on browser without putty

1.  go to aws console and select any instance -> (look on above tab) connect -> (look below do scrolling)connect

## PART 2

#### Project setup

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

5. run ifconfig cmd to know the ip address put it in browser

```sh
ifconfig
```

### About apache2 package structure

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

3. open index.html file with nano editor and modify it, then save it

- use "ctrl + k" for deletion

```sh
sudo nano index.html
```

4. Go to the browser to see the changes

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
