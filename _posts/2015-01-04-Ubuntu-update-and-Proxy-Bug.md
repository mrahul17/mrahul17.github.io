---
layout: page
---


In the past 1 month, I had received several updates from Ubuntu, but really didn't care to see all the bug fixes that were implemented.
I am now back to college and am compelled to use a proxy server for connecting to the internet. So, I decided to first change the proxy settings in ***system,git*** and ***apt*** . <a href="http://light94.github.io/2014/12/18/disabling-proxy-on-ubuntu-1404/">Earlier all these had to be set individually</a>. 

I first changed the system proxy by going to ***Network-->Proxy***. I had a gut feeling (:P) to test out whether apt picked up the global proxy or not, so I quickly did a ***sudo apt-get update*** and much to my woder, all the repository lists were successfully fetched!! This saved me from editing the apt.conf file.

Next, Git... inspired by the above change, I decided to test if git was also using the same proxy or not, so I quickly did a ***cd*** to one of my repo which I had ***staged already*** and did a ***git push origin master*** and again I found that it worked!!

I think, as per the observation above, that the bug has been fixed(I am trying to check out the details of the bug fixes in the last month). However, I won't claim that it will work similarly in every other ubuntu system as well.
