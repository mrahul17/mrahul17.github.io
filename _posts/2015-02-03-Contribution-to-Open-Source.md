---
layout: page
---

Till now, I had only heard how people develop passion for contributing to open source projects, but recently I have experienced it as well.
Though I am still a newbie in the world of open source, I have become addicted to it. I have found some open source projects to be very useful than the commercial ones, and I use them quite often. One such application is the ***command line tool*** called ***youtube-dl***, written in ***python***. This tool lets you download videos from ***youtube and a bunch of other supported sites***. The easiest example of its use it to download is like 

***youtube-dl video-url***

This obviously is just the surface, it offers many post processing options like extracting audio ,taking help of ***ffmpeg*** and file format conversion.

 As is evident from my other blog posts, I ***am behind a firewall and use proxy to connect to the internet***, so I always keep thinking of ways to reduce problems that arise from the above fact. One such problem is the error ***Connection Reset By Peer*** and I found that ***retrying download is the only possible solution to this***. I therefore edited the source code and added a condition to handle the error and it worked!! 
 I sent a [pull request](https://github.com/rg3/youtube-dl/commit/e77d2975afda3750104c90b7c0012c02a2a00b10) and it has been merged to the original project.

 This is a very active project and is giving support to download from other sites as well. Go ahead [fork it](https://github.com/rg3/youtube-dl) and make it even better!!