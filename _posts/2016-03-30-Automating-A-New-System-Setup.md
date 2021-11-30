---
layout: page
---

I recently purchased a new laptop, an HP Notebook to be precise. I had been preparing for this for about a week. The preparations included backing up all the data, creating a note of all softwares and python packages that I would be using and putting them in a installer script. I had been using the cool Mackup project for syncing all my dotfiles earlier, so configuration was not an issue. In the process, I got to know many interesting tips and tricks. Here are some of them:

- [This Stackoverflow answer](http://askubuntu.com/a/197532/340589) from **@funicorn** removes the pain out of updating the entire apt source when you just added a single ppa. *update-repo <tab> <tab>* .. only.
- Using the more actively developed *[redshift](http://jonls.dk/redshift/)* instead of the popular *f.lux*
- Create (at least) two partitions on yard hard disk. One for system files , other(s) for data. Upgrading your OS is much easier this way.This method is much more involved, but is worth the effort. *May [the force](https://help.ubuntu.com/community/Partitioning/Home/Moving) be with you*.
- Using dotfiles of other prople, there are a lot of them on Github
- It is important to have a fixed strategy for installing apps, [this answer](http://askubuntu.com/questions/1148/what-is-the-best-place-to-install-user-apps) just makes it super easy.

With an installer script ready, I just ran the script on my new Ubuntu installation. After requiring sudo password once, it ran all the way down, with 2-3 failures because of unpriviledged access to certain directories (and also because installation of some packages require a hell lot of other packages, I had to install these failed cases separately). 

In the process of setting up the system, I also had to modify certain files that I may never need to in future. This need may arise later as well. So, I have decided to make a note of all these files and put a special comment above the line(s) that I modify.


Chrome, Dropbox and some automation make life worth living.



 
