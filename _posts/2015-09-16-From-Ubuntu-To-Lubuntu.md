---
layout: page
---

I have been using Linux since 2013 on my old Acer laptop. I've never missed Windows, except once when I needed a good Word processing software.
Last year, the laptop showed symptoms like Image and text distortion when using multiple applications for a ling time. I usually had multiple terminal windows (terminator) and a code editor(Sublime) open . Consequently, I had to restart my system every four hours or so and it gave me a big headache to get back to my sweet configuration. I almost certainly knew that the problem was with the desktop environment(Gnome default) and/or the window manager. Since Linux offers so many choices, I did a little research and found that LXDE would best suit [my needs](http://askubuntu.com/a/65131). The following line from Wikipedia reaffirmed my faith 
> Tests with the default installation of Ubuntu show that LXDE 0.5's  memory utilization is lower than that of Xfce 4.6, which in turn   is lower than that of GNOME 2.29, with KDE 4.4 using the most RAM  compared to the aforementioned desktops. 

I decided to give it a shot and did a simple, 

```sudo apt-get install lubuntu-desktop```

 This action gives ***almost*** the [same result as installing pure Lubuntu](http://askubuntu.com/a/178030). It took nearly 10 minutes for the installation and on the next reboot, I was met with a bluish screen instead of the familiar Ubuntu's purple. Lubuntu impressed me since the first start and confirms all claims about being fast and less resource hungry. This was confirmed by the improved battery usage of my laptop. The problem of distored images also were not visible. The RAM usage is less than 50% most of the time , even when multiple applications are open. Unfortunately, I did not record RAM usage for the previous configration for accurate comparison.


Amidst so many advantages, Lubuntu is a bit buggy on my system (the bugs are known to the community but appear only in certain systems). Specifically, many a times Logout(```lxsession-logout```) does not respond properly and remains as a ongoing process even when you have resumed the session, so you have to manually end/kill the processes. There is also this problem with the [notifications system](https://bugs.launchpad.net/ubuntu/+source/lubuntu-artwork/+bug/1362555) where you get distorted themes  , though the latter has some workarounds. I am still in the process of finding workarounds for the other problems, but I must say that **[Lubuntu](net) is perfect** for what its meant to be, an OS for old hardware. From online discussions, I have learnt that it is highly customizable as well, though I have not yet given a shot as yet. The default file manager for LXDE , [PCMan] (https://en.wikipedia.org/wiki/PCMan_File_Manager) is way too fast than Nautilus.


Installing lubuntu-desktop over Ubuntu has certain demerits over a pure Lubuntu installation. Like duplicate software and background for the same purpose. This however has an easy solution, simply uninstall the applications and the daemons/ background-processes. The article at [psychocats](http://www.psychocats.net/ubuntu/purelubuntu) gives a hack to get *Pure Lubuntu* configuration.(A warning though, it might lead to uninstall of some necessary apps, so review the list before running). 

It goes without saying that the OS for my next laptop would definitely be Ubuntu, but for now I'll stick with Lubuntu.
