---
layout: post
title: SSH and Remote Desktop Setup Without Public IP
---

## SSH Setup

1. SSH with Public IP

    Just Login with that Public IP

2. SSH without Public IP

    Use Ngrok

    [ngrok - secure introspectable tunnels to localhost](https://ngrok.com/)

    1. Sign Up Ngrok (Free)
    2. Download and install the software; If you are in Linux or Mac system, move/copy the software to the /usr/local/bin than add the path to bashrc. In windows I don't know.
    3. Connect to your Account by: *ngrok authtoken [your key]* 

        ![image/Untitled.png](image/Untitled.png)

    4. Next step do this on computer which you want to remote:

        ![image/Untitled1.png](image/Untitled1.png)

        Your terminal will show like this

        ![image/Untitled2.png](image/Untitled2.png)

        Remember the ***Forwarding*** line

    5. At the other computer try to SSH with: 

        ***ssh [your_remote_computer_user]@0.tcp.ngrok.io -p [port]***

        Example:

        *ssh lontong@0.tcp.ngrok.io -p 9999*

## Remote Desktop Setup

Ubuntu Host - Mac Client

1. Install XFCE4 for each user

    [Install Remote Desktop (xRDP) for Ubuntu Server 18.04](https://gist.github.com/hehuan2112/54cca01be23973a9f8b369e8d0df216e)

2. Remove 2 xRDP max remote desktop

    ![image/Untitled3.png](image/Untitled3.png)

3. Install XRDP Client

    [‎Microsoft Remote Desktop 10](https://apps.apple.com/app/microsoft-remote-desktop/id1295203466?mt=12)

## Adding Ubuntu 18.04 User

1. Open Settings
2. Users and Group
3. Add Admin User
4. Reboot