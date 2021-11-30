---
layout: page
---

I just wrote a [python script](https://github.com/light94/questionPapers), using ***Beautiful Soup*** to download ***all*** question papers from my college server. (yes, the all has some exceptions now, but I will soon remove it).
For the 3 years that I have been in my college, I have found that in every exam season, the server crashes because children (more than 10,000 in number) begin the downloading around the same time.
We have alternatives, like ***DC++***, but who would take the pain of downloading all files and sharing it on the hub? 

So,I wrote the script, because I didn't want to take the pain either, but still wanted to help the community. The script makes a very neat directory structure to store the question papers.

I had observed that upto the year 2007, a differet mode of storage was being used than after it. To be elaborate, upto 2007 it was ***Year->Department->Courses*** while after it, it was ***Year->Phase->Department->Courses***<br>
So, I have written 2 scripts to cater to the different needs. Ofcourse,they can be combined in to one.<br>
I learnt a bunch of new things. 
First, if you are behind a proxy and have configured your system to work with it, then you have 2 options for this script to work. Either use the ***dconf editor*** (yes, I work on Ubuntu) or use these lines:

***proxy_support = urllib2.ProxyHandler({})***<br>
***opener = urllib2.build_opener(proxy_support)***<br>
***urllib2.install_opener(opener)***<br>

What this does is that, it creates a new ***Proxy Handler*** that will not use your default proxy settings. In fact, the proxy handler is set to access the internet without proxy.

Second, a very nice way to create directories (courtesy:[SO](http://stackoverflow.com/a/273227/3363206))

***if not os.path.exists(directory):***
    ***os.makedirs(directory)***

Also, regular Expressions, since I had to make neat directory names. [This page](https://docs.python.org/2/library/re.html) really helped me a lot. Few things to keep in mind are that special characters loose their meaning inside '()'. Also if you need a regexp to match '(' or ')' , you can escape it like this '\\('

As earlier said, some question papers could not be downloaded because of encoding of directory names. I will update later.

Cheers!!

