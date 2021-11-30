---
layout: page
title: Post Jekyll Installation
tags: [jekyll]
---

I just finished up importing my blog articles from ***Google's Blogger*** using the ***jekyl-import gem***. 
The gem has to be installed separately since it provides functionality that is not needed as a core part of jekyll.
The gem allows importing your blog articles from many different platforms like ***wordpress, durofy etc*** (and also blogger as mentioned above).

I initially used to blog on [http://justanotherlearner.blogspot.com](http://justanotherlearner.blogspot.com) and I followed the instructions given on [http://import.jekyllrb.com/docs/blogger/](http://import.jekyllrb.com/docs/blogger/) to import my posts as ***xml*** and then publish them on this new platform.

Everything worked out fine, the imported posts were now in my ***_posts*** folder , but wait! the owner is ***root***. As mentioned in previous posts, its not advisable to use sudo to do trivial tasks like editing a file. 

The soution to the problem is to simply change the owner of the folder by the following command.

'***sudo chown - - recursive rahul:rahul _posts***'

 (The - -recursive flag as expected will apply the changes to all the folders within the posts folder recursively.)

P.S: Don't mind the extra space between the 2 dashes there, that's what ***Markdown*** did :P