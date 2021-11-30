---
layout: page
---

I had this task of configuring a remote server to host some websites of my college. This post is a compilation of the steps I performed to get things working as well as the sources that I found along the way.


To ease things a bit, I got ubunutu installed on the server and the DNS was configured to assign the server's ip to the url's (I hosted 2 websites on the same server). After this, I began the configuration. 

I connected to the server using the ***Remote Desktop Viewer*** app. After that my first job was to install xampp. I headed to the [xampp website](https://www.apachefriends.org/download.html) and downloaded the latest xampp installation file on the server.Installing it was really easy:<br>
`cd download_directory`<br>
`sudo ./xampp-linux-x64-1.8.3-3-installer.run`

The installtion asked the location of installation folder, I just left it to the default i.e ***/opt/lampp***. The process took roughly 2 minutes.

After this, `sudo /opt/lampp/lampp start` started the apache and mysql servers and I could use the url only to be a met by a ***new security feature of xampp*** page. I tried searching for how to bypass that page , and finally decided to comment out the section in ***/opt/lampp/etc/extra/httpd-xampp.conf*** that was causing this page to show up. <br>

<img src="{{site.url}}/assets/images/Screenshot from 2015-02-27 20:36:29.png" height="440px">
After doing this and restarting the server with ***sudo /opt/lampp/lampp/restart***, I was instead met by a cute ***xampp splash screen***. There were lanuages to chose from and ***you could login you without password***!! Obviously, this had to amended and sure enough, the last line of the page said that  this could be done using `sudo /opt/lampp/lampp security`.

This was indeed cool!! I was asked to set password for each and every component of the installation and I used the same password everywhere -_-. That done, I reloaded the page to find that it indeed was asking me the password. 

The task now remained to put the website files to ***/opt/lampp/htdocs*** (the ***default*** location where website directories are created). Since I had the website already hosted on git, I used ***wget*** to download the zipped file from gitub. But this could not be done in one go, since I was behind a proxy. <br>
`export http_proxy='<proxy_address>:<port>'`<br>
`export https_proxy='<proxy_address>:<port>'`
did the task of configuring proxy. Note that this is only a one time solution. Once you restart the shell, you would have to do it again. However, I would not need it, so I was satisfied with this solution. Also, the default permissions for the htdocs folder are as follows:

***user :root***<br>
***group :root***<br>

This has to be changed, if ***you/apache*** have to create a file in this directory. By default, apache2 belongs to the ***daemon*** group. The convention is to make a new group called ***www***. [This question](http://superuser.com/a/268996/402332) on SO addresses this issue brilliantly. Go ahead and follow the steps there and come back to proceed. Make sure to change the group of apache2 to www in `/opt/lampp/etc/httpd.conf`. <br>
P.s : the ***blub*** in `$ sudo usermod -aG www blub` is the username with which you logged in to the server.<br>

So, I downloaded the file, ( it took an hour for this), unzipped it and moved it to the htdocs folder. The htdocs by default has a ***index.php*** which is responsible for showing you the splash screen. That can be renamed or removed once you are ready to host the website.

Now, the server was to be instructed to look for files in it rather than on the internet when request was made to it, and I feel that I can not write it better than has been written in [this blog](http://www.devarticles.in/linux/creating-new-virtual-host-while-using-xampp-in-ubuntu-linux/). Following all the steps exactly, I was able to launch both the websites. They are hosted at [alumnimeet.iitkgp.ernet.in](alumnimeet.iitkgp.ernet.in) and [mentorship.iitkgp.ernet.in](mentorship.iitkgp.ernet.in).

I hope this post turns out to be useful in case you are in the same situation. 

Cheers!!