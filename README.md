# nginx-2420
## Nginx Tutorial
By: Jessica D.
Date: 4/9/2024

# Prerequisites
You must meet these prerequisites to follow this tutorial.
- [ ] Vim is installed
- [ ] Nginx is installed

Worry not, if you do not meet these requirements the guide will take you through the installation.

## Good Habits
Before intallation of the prerequisites a good habit to have is to always update your system when you start it up. Use the following command to do so:
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

Well done! If you were successfully able to install the prequsites you are now able to begin the Nginx configuration.

# Nginx configuration
Now, that we have Nginx installed we need to configure it to meet our needs.

## Starting and Enabling Nginx
We now must start and enable Nginx for it to actually work. Begin by starting it then enabling it with the following commands.
```
sudo systemctl start nginx
sudo systemctl enable nginx
```
These commands should've started and enabled nginx and we can test this by inputting the following command:
```
sudo systemctl status nginx
```
This should output Nginx's status, please refer to the "NginxStatus" image as a reference.

