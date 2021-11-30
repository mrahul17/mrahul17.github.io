---
layout: page
---

Over the past year, I have been discovering what all linux has to offer and the process is going on.
Recently I found some things that have greatly increased my productivity as a web developer. I need to have multiple terminals open on my screen (or maybe multiple tabs), one for connecting to the server, one for browsing local files, one specially for git (cannot really miss that) and maybe one another as per demand.
There are many alternatives for this [here](http://alternativeto.net/software/terminator/). But I chose ***terminator*** after trying a few others, because it offers a lot of features, like opening multiple sessions in a grid and a drag and drop functionality to arrange the terminals as well as a lot of keyboard shortcuts. It can save your preferences so that the next time you open termianl, you can it the way you left it back!!.
So, if you often find your workspace cluttered with terminals and you instead want it to look something like this


<img src="{{ site.url }} /assets/images/Screenshot from 2015-01-24 21:39:21.png" height="400px">
 go ahead and follow this procedure.

Fire up your terminal and write:
***sudo apt-get install terminator***
Once installed type terminator to launch your new installation. Create a layout you like by ***splitting the screen horizonatally or vetically*** by right clicking on the terminal and selecting the appropriate preferences. Next,go to ***Preferences->Layout*** and name your current layout and save it by a name you can remember well.
Next, time when you want to reload the configuration, type ***terminator -l configurationname*** . (put the name of your configuration here).

[Here](http://linux.die.net/man/1/terminator) is a reference for keyboard bindings for terminator.


The next tweak is something more general, ***using aliases in place of the long terminal commands***. In Ubuntu you need to open the ***bash_aliases*** file and add your custom aliases. 
For example:<br>
***alias aptinstall="sudo apt-get install"***<br>
***alias aptupdate="sudo apt-get update"***

and save this. Now if you type ***aptupdate*** in the teminal, it will run ***sudo apt-get update***. You can do the same for git commands like ***git push origin master***, ***git commit -m*** etc.
I found this to be really useful and hope you too will.

Cheers!! 
