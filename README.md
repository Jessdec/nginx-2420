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
