---
layout: post
title: SSH and Remote Desktop Setup Without Public IP
---

Here is my walkthrough. 

1. SSH with Public IP

    Just Login with that Public IP

2. SSH without Public IP

    Use Ngrok

    [ngrok - secure introspectable tunnels to localhost](https://ngrok.com/)

    1. Sign Up Ngrok (Free)
    2. Download and install the software; If you are in Linux or Mac system, move/copy the software to the /usr/local/bin than add the path to bashrc. In windows I don't know.
    3. Connect to your Account by: *ngrok authtoken [your key]* 

        [<img src="/public/images/ssh-remote/Untitled.png" style="width: 800px;"/>]({{ site.baseurl }}/)

    4. Next step do this on computer which you want to remote:

        [<img src="/public/images/ssh-remote/Untitled1.png" style="width: 800px;"/>]({{ site.baseurl }}/)

        Your terminal will show like this

        [<img src="/public/images/ssh-remote/Untitled2.png" style="width: 800px;"/>]({{ site.baseurl }}/)

        Remember the ***Forwarding*** line

    5. At the other computer try to SSH with: 

        ***ssh [your_remote_computer_user]@0.tcp.ngrok.io -p [port]***

        Example:

        *ssh lontong@0.tcp.ngrok.io -p 9999*
