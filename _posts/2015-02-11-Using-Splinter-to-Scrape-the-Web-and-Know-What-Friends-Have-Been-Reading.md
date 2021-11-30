---
layout: page
tags: [python, hacks, web-scraping]
---

There was no way in which people at my college could know ***what books their friends had been reading***. Although the library website makes it easy to do this by not asking the password, still you need to go through the pain of typing in the roll numbers one by one. Also, crawling the library website was relatively difficult as it ***loaded content lazily using javascript***. I found out that splinter makes crawling such websites easier. It mimicks user interaction with a browser with the help of code. Actually, ***splinter is a wrapper around the selenium package***. In fact selenium webdriver can be though of as an api to access browsers with code.


I installed splinter in a virtualenv and set about writing the code,verifying my code by manually executing the actions. It was really amazing to find the ***2 Way Binding***, that is, what you do manually on the instance of the browser launched will be reflected in code and vice versa. After learning the API, it was easy to write the script. One point where i got fixed was when then entire script was fed to the console at once( rather than giving commands one by one), ***selenium throwed an error saying that element was not found in DOM***. This seemed confusing , especialy because no such error came up when giving commands one at a time. However, the error description made a lot of sense when I thought about it: when I was giving the commands one by one, the browser got its time to fetch all resources and build up the final DOM.When I feed the entire script at once, the commands that depended on the DOM could give error since the DOM was not fully built, that is, some nodes that you are referencing in your code might not be even existing in the DOM at that time.
As, can be seen in my code, I compensated for this by pausing script execution using ***python's time module***. With that, the errors were gone and the script fetched the data exactly.

My code is hosted at github [here](https://github.com/light94/library-issues) .

P.S: It is really cool to watch the browser open webpages and click links without laying a hand on your keyboard!!
But it is not necessary to launch the browser for this purpose. You can use the so called ***headless drivers*** that do not open the browser to run the actions, it is all done in the background. Have a look [here](http://splinter.cobrateam.info/en/latest/index.html).