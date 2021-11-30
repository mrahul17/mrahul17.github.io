---
layout: page
---

This post is about installing R and R Studio on Ubuntu. 

First, fire up the terminal and the R source in the repository list
***sudo add-apt-repository http://cran.cnr.berkeley.edu//bin/linux/ubuntu/trusty/*** 

P.S *http://cran.cnr.berkley.edu* is what I used. You can choose your faviourite from [the list of alternate mirrors](http://cran.r-project.org/mirrors.html).

Now, this has been added to the list of sources from which ubuntu can download packages. But,it still does not know what all packages are available. So, you need to update the package listings.
***sudo apt-get update***

Now, install R
***sudo apt-get install r-base***

This will install command line utility for R. If what you need is just this, then you are done!!
If you need a GUI too, you need to install R Studio.

So, go ahead and download it [here](http://www.rstudio.com/products/rstudio/download/)
I did it via console,once i got the package name correctly for my architecture.
***wget rstudio-0.98.1091-amd64.deb***

Then install it 
***sudo dpkg -i rstudio-0.98.1091-amd64.deb***

and you are done!!
search for R Studio and click, boom!!
