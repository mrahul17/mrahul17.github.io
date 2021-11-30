---
layout: page
---

JHBuild is a tool developed by ***Gnome*** that lets you build and run Gnome modules in a sandbox environment so that global settings are not affected. Originially developed for building Gnome, it is now used in other projects as well.

I recently used JHBuild to install gnome-maps on Ubuntu. The installation instructions given [here](https://wiki.gnome.org/GnomeLove/BuildGnome) are accurate and elaborate. After this is done, we can use ***jhbuild*** directly at the terminal.

Please note that JHBuild comes with a GUI as well where you just need to select the module which you need to install.

Now, the problem which I was facing was that , khbuild was unable to download dependencies from gnome's git repositories automatically. Around 56 repositories had to be downloaded and each was failing with the error ***Unable to fetch git://git.gnome.org/repo_name***. Although JHBuild gives the option to fire up the terminal and manually download the repositories , but doing this for 56 repositories is a real pain. So, I set about finding an alternative.

I found that when I copy paste the url on the address bar of the browser, it is redirected to a url like ***http://git.gnome.org/browse/repo_name***.
I also found that JHBuild ***should have a configuration file ~/.config/jhbuildrc***. See [here](https://developer.gnome.org/jhbuild/unstable/config-reference.html.en). (It was not there in my case, so I created one there.)
I added the line:

***repos['git.gnome.org'] = 'http://git.gnome.org/browse'*** 
and saved the file.

and then JHBuild started working as per expectations, downloading and installing repositories on its own.
