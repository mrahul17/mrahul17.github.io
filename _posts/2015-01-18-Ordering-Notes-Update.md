---
layout: page
---

My post over [here](http://light94.github.io/2014/11/15/ordering-your-notes/) proved to be useful to some of my friends and they asked me how to use it. So, ***this is a small post about how the script can be used***.


***UPDATE***:
I have published a python package [***rotnotes***](https://pypi.python.org/pypi/rotnotes/0.1) which will make using the script a lot easier

Just do ***pip install rotnotes***. Please note that the script uses an additional library ***Pillow***.

Usage:

`>>>import rotnotes rotnotes.rename('path_to_your_notes_directory')`
or
`>>>rotnotes.rename('path_to_your_notes_directory',True)` #to rotate notes as well

Head over to the [github repo](https://github.com/light94/rename-notes) to contribute and suggest changes.


**Deprecated**:<br>
***Method 1***:

Open terminal and cd to the directory containing the images. Next ***copy paste the entire script in terminal and press return***.

***Method 2***:
This method involves the ***Nautilus Actions Configuration Tool***. I have writen about it [here](http://light94.github.io/2014/11/05/hacking-with-nautilius-actions/). You just need to ***change the path of the command to where you have stored the rename-notes.py file***.

Another methods involve modifying the script to accept the directory path in the console itself.

Cheers!!
