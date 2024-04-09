# nginx-2420
## Nginx Tutorial
By: Jessica D.
Date: 4/9/2024

# Prerequisites
You must meet these prerequisites to follow this tutorial.
- [ ] Vim is installed
- [ ] Nginx is installed

Worry not; if you do not meet these requirements, the guide will take you through the installation.

## Good Habits
Before installation of the prerequisites, a good habit to have is to always update your system when you start it up. Use the following command to do so:
```
sudo pacman -Syu
```

## Install Vim
Use the following command to install Vim:
```
sudo pacman -S vim
```

## Install Nginx
Use the following command to install Nginx:
```
sudo pacman -S nginx
```

Well done! If you were successfully able to install the prerequisites, you are now able to begin the Nginx configuration.

# Nginx configuration
Now that we have Nginx installed, we need to configure it to meet our needs.

## Starting and Enabling Nginx
For Nginx to work, we must start and enable it. To do so, use the following commands:
```
sudo systemctl start nginx
sudo systemctl enable nginx
```
These commands should've started and enabled nginx, and we can test this by inputting the following command:
```
sudo systemctl status nginx
```
This should output Nginx's status. Press Ctrl + c to exit this menu. If needed, please refer to the "NginxStatus" image.

## Configuring Nginx for Web Page Display
Start by navigating to the root folder:
```
cd /
```
Create a new directory in root:
```
sudo mkdir -p /srv/2420-files
```
Navigate into the newly created folder:
```
cd /srv/2420-files
```
## Edit the Nginx Config
Navigate to the nginx.conf file location and open the nginx.conf:
```
cd /etc/nginx/
sudo vim nginx.conf
```
While in ESC mode once you are inside the config, remove all the lines of code inside by typing and entering the following:
```
d300
```
This deletes 300 lines. You may change this number to work for the amount you need to remove.
Now enter insert mode by pressing the 'i' key and copy and paste the following in:
```
user http;
worker_processes auto;
worker_cpu_affinity auto;

events {
    multi_accept on;
    worker_connections 1024;
}

http {
    charset utf-8;
    sendfile on;
    tcp_nopush on;
    tcp_nodelay on;
    server_tokens off;
    log_not_found off;
    types_hash_max_size 4096;
    client_max_body_size 16M;

    # MIME
    include mime.types;
    default_type application/octet-stream;

    # logging
    access_log /var/log/nginx/access.log;
    error_log /var/log/nginx/error.log warn;

    # load configs
    include /etc/nginx/conf.d/*.conf;
    include /etc/nginx/sites-enabled/*;
}

```
Press ESC to exit insert mode, and now save and quit by typing:
```
:wq
```

## Creating Folders for Enabling/Disabling Website
Navigate to Nginx within the etc directory:
```
cd /etc/nginx
```
Create two new folders within Nginx:
```
sudo mkdir sites-enabled
sudo mldir sites-disabled 
```

Navigate into each file and repeat this process for each of them
```
cd sites-enabled or sites-disabled
sudo vim nginx-2420 
```
Copy and paste this into each of the new files:
```
server {
    listen 80;
    listen [::]:80;
    server_name _;
    root /srv/2420-files;
    location / {
        autoindex on;
    }
}
```
Save and exit back to the console. To test if this has been done successfully, input the following command:
```
sudo nginx -t
```
