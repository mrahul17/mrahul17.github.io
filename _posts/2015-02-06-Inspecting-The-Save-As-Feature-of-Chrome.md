---
layout: page
tags: [python,web-scraping]
---

Due to my recent webscraping project, which was to download all the chapters of a book to be able to read them when offline (Disclaimer: the book is free to read online), I was able to delve into the ***Save As featue of Google Chrome***.<br>

***How I reached there?***<br> There were more than 45 chapters to save. Though its not a big number, still requires considerable time. So, I set about writing a python script that would do the downloading for me. I tried to download the page simply with ***urllib2*** and save it in ***".html"*** format. But it did not work. I got only the text (actually the HTML) out of the page. The resources like ***css files and images*** were all lost during the download. Actually, downloading the webpage in this way mimicks the old method of saving webpages, that saved only the HTML. However, ***if the webpage had contained inline css, I would get the required styling too*** , only images would be absent then This feature is present even now (atleast in Google Chrome), but is not the default, as can seen in the screenshot below:<br>
<img src="{{site.url}}/assets/images/html-only.png" height="400px">
***The Save As***<br>
So, I manually saved the page as ***webpage,complete*** using chrome and went to the download location to find the html file and a new folder with the name name. I inspected the html file and found that ***relative urls for css files had been replaced by full path to the repective resource***,but resources like images and javascript were stored in the folder locally and their path had been modified to link to those files instead. I understand why images and javascript were stored locally,but why not the css files? Also, not all css files were linked this way, the files describing ***additional fonts*** were downloaded locally, just like the images and javascript files. 

Looking closer, I found a difference in the way these css files were referenced, they had a ***type = "text/css" attribute*** (the ones that were downloaded had this). I confirmed this fact by downloading certain other webpages too. So I concluded:

***If your css's link tag has the type attribute,it will be downloaded when you save the webpage, else not.***

Now, most good sites have same styling on all their webpages. Also they had links to the same set of javascript files. ***So that would mean that I needed to download the css and javascript files only once*** (in reality if I had downloaded all the webpages manually, I would get 35 html files and 35 folders with each folder having almost the same content, apart from images and miscellaneous). With this folder ready, I could download the html using python. But this was not the end. For each page to be viewed properly, the resource path should be correct. When we download the webpages manually, the page and the corresponding folder are given name corresponding the title of the webpage. So, after I downloaded each html file, I had to replace the folder name with the ***only folder*** containing the resources ***and check if it had all the required images to render the page properly***. This can be done ***using regexp***. First scan for the resource, given the title of the webpage and then replace it by the single resource folder that was initially downloaded.

Cheers!!