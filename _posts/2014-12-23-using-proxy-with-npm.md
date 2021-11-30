---
layout: page
tags: [npm,proxy,linux,ubuntu]

---

Today I had been trying to install few node packages with npm. I had installed npm earlier when i was accessing internet from a proxy server. As usual i had installed it from the command line and it appears that npm picked up proxy settings from the global settings, so all was working fine. But now, that  I was accessing the internet directly, i found that npm wasn't working as it was expected. I must say in this regard that apt-get offers a helpful debugging feature , it tells the address of the proxy server it is trying to connect to (if it is trying to connect to one). IN an earlier post I have written about how to clear proxy settings from apt-get.

Now, in my command line npm was stuck at one point, no error message,nothing. After trying out a few things like 

   ***npm clear cache***

I realized that proxy might be an issue for this. So, i went about changing the configuration like this:

   ***npm config set proxy false***
   ***npm config set https-proxy false***

Fortunately, in my case, it worked out. I say fortunately because npm was giving no debugging hints.


That said, your problem might be ***just the opposite***

You can set proxy for your npm like this:

   ***npm config set proxy http://proxy_host:port***

There are however some issues regarding this, but <a href = "http://stackoverflow.com/a/13138231/3363206"> this answer</a> addresses and solves them. 