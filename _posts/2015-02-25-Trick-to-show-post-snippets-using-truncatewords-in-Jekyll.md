---
layout: page
---

***UPDATE (28/3/2015)***:
I recently realized how easy it is to implement the plugin system in Jekyll. If you want an easier method as compared to the one given earlier, just create a folder called ***_plugins*** in your site root directory and copy [https://github.com/light94/jekyll-plugins/blob/master/closeformat.rb](this file) into it. This will automatically be loaded when you restart jekyll. It registers a filter with Jekyll, called ***close_format***.  You can fork [https://github.com/light94/jekyll-plugins/](this repo) and suggest more functionality.


***Original Post***:
Scrolling down this page you will find that I have listed some of my blog posts, sorted by date and showing some portion of the actual content. What you may not notice is that each snippet contains ***exactly the same number of words***. If you are quite familiar with jekyll, you might know that post nippets can be shown with the help of ***post.excerpt***. By default, post. excerpt grabs the first paragraph of your post and displays it as a snippet. This works for most people, but as of writing this post, I did not like it since the introductory paragraphs of my posts vary greatly and ***I find that ugly***.

To deal with it, ***Liquid*** ( the templating engine jekyll uses by default) has a filter called ***truncatewords*** which cuts down a string to a given number of words. So does it sound like ***that's it***?<br>
Well no, ***truncatewords*** was not built for this purpose and therefore does not achieve our mission gracefully. The problem I faced was that, suppose you truncate your post to 50 words and just after the 50th word, there was a closing `<em>` or `<strong>` tag. Liquid will not attempt to close the tag (because as I said, the filter was not made for this purpose). As a result, subsequent characters will adopt the formatting of the 50th word until the tag is closed. A lot of questions on SO try to address this issue and one of the solutions is to use the ***strip_html*** filter. It literally strips out all the html tags leaving behind ***play and ugly text***.

So, I cam e up with 2 hacks, the first is easier and here it goes.<br>
The code for displaying a list of posts is [here](https://github.com/mdo/jekyll-snippets/blob/master/posts-full.html). <br>

<img src="{{site.url}}/assets/images/Screenshot from 2015-02-25 01:37:10.png" height="200px">


In order to see the snippets, you need to pass the ***post.content*** through the ***truncatewords*** filter like this :<br>

<img src="{{site.url}}/assets/images/Screenshot from 2015-02-25 01:41:42.png" height="30px">
This will limit the number of words to 200. Now comes the hack. To close any unclosed `<em>` or `<strong>` tags, we supply the closing tags ourselves. Here is the final code. <br>


<img src="{{site.url}}/assets/images/Screenshot from 2015-02-25 01:39:03.png" height="200px">



This little trick achieves our goal but there is a high chance that we supply a large number of ***unrequired closing tags***. 

So, here goes the next hack, where you create a filter for closing the unclosed tags. The logic goes like this: we count the number of unclosed tags and supply ***only*** the required number. The code is here.

<img src="{{site.url}}/assets/images/Screenshot from 2015-02-25 01:40:11.png" height="250px">



where ***head*** contains the truncated string. Passing the string to the above function will supply the required closing tags. In order to use it, you can download the git repository of liquid and place this code in lib/liquid/standardfilters.rb and then install liquid or you can use it as a standalone function. 

P.S: I am working on converting the above code to a ruby gem and will update here once it is published.

