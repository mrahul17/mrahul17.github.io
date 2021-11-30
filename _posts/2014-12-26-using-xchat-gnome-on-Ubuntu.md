---
layout: page
tags: linux
---
Recently I started using ***empathy*** as an ***IRC client*** on Ubuntu. As per the reviews and the <a href = "https://wiki.gnome.org/Apps/Xchat-Gnome/FrequentlyAskedQuestions#Changing_proxy_settings"> official documentation</a> , empathy is ***currently not a very good irc client***. It has some bugs, recently I too reported a bug regarding change of nick in empathy.

So, I switched over to ***xchat-gnome*** , a gnome irc client. It has a decent UI and is full of features, which are currently lacking in empathy. I found that xchat-gnome picks up proxy setting from the previous client. I would not say that it picks up the gloabl settings but from ***the previous client*** (atleast in my case).

<a href="https://wiki.gnome.org/Apps/Xchat-Gnome/FrequentlyAskedQuestions#Changing_proxy_settings">This page</a>gives some understanding about how you can change the proxy setting, though its not very clear .Another article , [here](https://toxin.jottit.com/xchat_set_variables) explains how it can be done very easily. 
A total of **7** variables might have to be modified to give you the proxy configuration you desire.
net_proxy_auth = 
net_proxy_host = 
net_proxy_pass = 
net_proxy_port = 
net_proxy_type = 
net_proxy_use = 
net_proxy_user = 

The conclusion is that xchat-gnome does not have a GUI for proxy settings, but it ***does*** support proxy. 

**Update**:
I have found an alternate way to modify xchat-gnome settings. This method uses editing the configuration file directly in the text editor. 

You need to ***cd*** to the ***.xchat2*** hidden folder and ***sudo gedit xchat.conf*** . In this file you can find all the settings listed and you can edit them as per requirements. The description of each of these variables is available at  <a href = "https://wiki.gnome.org/Apps/Xchat-Gnome/FrequentlyAskedQuestions#Changing_proxy_settings"> official documentation</a>.

Cheers!!

