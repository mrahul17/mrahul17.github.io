---
layout: page
tags : [ubuntu,hacks]
---

I just started using the ***Gnome Shell*** on my Ubuntu 14.04 instead of the usual ***Unity*** and I really liked it . Keeping an option of both Gnome and Unity is simple enough. You need to issue 2 commands :

   ***sudo apt-get upgrade***

   ***sudo apt-get install gnome-session-fallback***

A more detailed description is already given <a href="http://www.techienote.com/2014/04/how-to-switch-to-gnome-desktop-environment-in-ubuntu-14-04-trusty-tahr.html">here</a>.

I liked Gnome shell a lot and decided to learn more about it in order to contribute to it. Today has been a lot of googling and learning. This post is a summary.

To begin with , <a href="http://superuser.com/a/41863/402332"> this answer on superuser </a> gives a very good foundation to understand what gnome is. Please note the comment given by @sleske there.

This <a href="http://lifehacker.com/5762081/wtf-desktop-environments-gnome-kde-and-more-explained/all">awesome article</a> gives the difference between a desktop environment and a windows manages (the difference pointed in the comment above). I'll copy paste the important stuff here.
 
_Linux's GUI is completely separate from the operating system itself. It's split up into a few different parts: atop the command-line operating system is the X window system, which is what draws the GUI onto your screen. On top of that is what's called your window manager, which allows you to (surprise, surprise) manage the windows on your screen: move them around, drag and drop files, scroll up and down, and so on._


_You can get a usable GUI with just a window manager, though it's fairly minimal. You usually won't have any panels, taskbars, or a ton of menus to work with, so there's a bit of a learning curve. It may work for low-powered machines, but more often, people use a window manager coupled with a desktop environment, which lets you choose between different taskbars or docks, customize the appearance of your system, and tweak settings through the GUI_




_Gnome, developed by the Gnome project is a desktop environment which is composed entirely of free and open source software. Although mainly targeted toward linux, it is also supported on other operating systems._

Put simply, ***Gnome is a desktop environment*** while ***gnome-shell*** is a graphical shell of the Gnome desktop environment and is tightly integrated with ***Mutter***, a window manager. 

A window manager is a software that manages the placement and appearance of windows in a GUI 

Graphical shells provide means for manipulating programs based on graphical user interface (GUI), by allowing for operations such as opening, closing, moving and resizing windows, as well as switching focus between windows. (more detailed explaination will be added soon).




