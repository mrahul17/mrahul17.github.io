---
layout: page
---

This time I voluntarily took the job of mass mailing. No, I didn't spam anyone. It was an informational mail to be sent to the alumni of my collge.
As is evident from my earlier posts, I always have to workaround for proxy settings. Although there exist applications that provide inbuilt support for proxy, like ***Thunderbird*** for mailing, I decided to try something new, the [Mailgun api](http://www.mailgun.com/). It truly is what it says , ***The Email Service For Developers***. Sending email with the api is damn easy. All you need to do is to create an account and optionally verify your custom domain. It has documentation explaining how to send as well as recieve emails (for recieveing you need to adjust some more settings for your DNS). <br>This post is about how I used mailgun for mass-mailing and an additional insight I got about the mailing service.

I created a csv file having only the email-id of the recipients. Though I could have also used the raw code which mailgun provides for sending mails, I decided to use a [python package](https://github.com/ZeroCater/python-mailgun2) built upon the raw code, that makes it relatively easy to send mails. Just do a `pip install mailgun2` .	<br>

The way to send single mails using this package is  <br>
`from mailgun2 import Mailgun`<br>
`mailer = Mailgun('apikey', 'example.mailgun.org')`<br>
`mailer.send_message('from@yourdomain.com', ['to@you.com', 'others@you.com'], subject='Hi!', text='Sweet.')`

As is evident, for my case I had to loop this over for all the ids. I used the ***csv module*** for this<br>
{% highlight pythonn %}
    
import csv
filehandle = open("path to my attahcment file")
filename="path to csv file"
with open(filename,'r') as f:
		csvreader = csv.reader(f)
		for row in csvreader:
			if len(row)>0: #checking for blank fields
				mailer.send_message(
   					'from@yourdomain.com',
    				['to@you.com', 'others@you.com'],
    				subject='Hi!',
    				text='Sweet.',
    				attachments=[List of (file name, content type, file handle)]
    				)

{% endhighlight %}
    
If you don't look closely, the above code looks good and sure enough I tested it by putting a single email id in the csv file, and I got the email almost instantaneously. However the code above has a major flaw. When you are sending the mail, using the ***send_message*** function, it is behind the scenes executing `filehandle.read()` in order to send the ***entire content of the attachment to the recipient***. Note that I have declared this variable outside the loop, which means the next time I use te file handle as attachment, `filehandle.read()` actually reads ***None***. So while your recipients see that the mail has an attachment, its size turns out to be ***0 Bytes***. 

The obvious solution (the one which came to me) was to ***open the file within the loop*** so that after sending each mail, all the contents are read in again. Sure enough, this solution was correct and all the recipients got a valid attachment in their mail.

