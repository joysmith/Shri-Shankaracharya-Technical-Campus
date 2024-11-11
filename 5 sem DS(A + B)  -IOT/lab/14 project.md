# Create Linux Instance - Implement Apache Web Server on Linux Instance

### PART 1

1. Go to aws console, select asia-pacific mumbai region
1. Create ec2 instance: service -> compute -> ec2 instance
1. Select "running instance"
1. Select "launch instance", then
1. Select "ubuntu" image as an OS as t2-micro (free one)
1. (optional: only for putty and other ssh)Create key-pair login ".pem"
1. ✅ Allow HTTPS traffic from the internet
1. ✅ Allow HTTP traffic from the internet, then launch server
1. Select "connect to server"

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
