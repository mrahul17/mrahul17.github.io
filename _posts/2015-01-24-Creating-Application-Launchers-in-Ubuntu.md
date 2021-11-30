---
layout: page
tags: [hacks]
---

A remarkable feature that I observed in Linux is that applications installed do not automatically create a shortcut icon for themselves and ***unncessarily clutter the desktop***. They instead leave it to the user whether they would like to lock it in the Unity Launcher or create a shortcut on desktop.
However, it is not very intuitive how to create launchers of applications manually. This post is about how you can create a launcher for ***applications that you know how to launch from the terminal*** (and that means ***all*** the applications).Essentially, you must know the command used to launch the application from terminal.

To proceed, install ***gnome-tweak-tool***. This will certainly make your life easier in future as well.
***sudo apt-get install gnome-tweak-tool***<br>
As a part of the gnome-tweak-tool , ***gnome-desktop-item-edit*** is also installed, which is what you will use to create a shortcut.<br>
***gnome-desktop-item-edit --create-new ~/Desktop*** <br>
This is what you will get.
<img src="{{site.url}}/assets/images/Screenshot from 2015-01-24 22:15:10.png" height="200px">

I will now proceed in reference to my last post reagarding installation of ***terminator***. Further, I had configured terminator to ***display 3 termianl windows on startup***.
Type in the name of your application, it need not exactly match the official name. 
Next, type in the command you use to launch the app in terminal. In case of terminator I use ***terminator -l 3terms*** (where 3terms is the name i gave to the configuration).
Next is a not required comment regarding the launcher.
After filling it up, this is what my screen looks like.
<img src="{{site.url}}/assets/images/Screenshot from 2015-01-24 22:26:51.png" height="200px">

Click Ok and you are good to go. You will find the fully functional icon on your screen.

Cheers!!


