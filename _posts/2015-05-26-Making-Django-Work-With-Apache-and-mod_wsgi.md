---
layout: page
---

Finally, a post after  a long time!!

I have created some Django apps in the past and they were generally for  learning and therefore the code was never shipped to a production server. However, a recent project that I am doing during my intern, required me to get the code up and running on a production server.

I read that  [Deploying Django with Apache and mod_wsgi is a tried and tested way to get Django into production](https://docs.djangoproject.com/en/1.8/howto/deployment/wsgi/modwsgi/) and so went on to deploy my project using Apache. I came across various good sources, especially [the one on Code Ship](http://thecodeship.com/deployment/deploy-django-apache-virtualenv-and-mod_wsgi/) which was somewhat related to the one on [Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-serve-django-applications-with-apache-and-mod_wsgi-on-ubuntu-14-04). In this article, I have tried to combine the information present in these blogs with  some  customization.

Apache server has no inbuilt feature to serve python apps. It can however do so by using a package called ***mod_wsgi*** that can host python applications that conform to the [WSGI](http://wsgi.readthedocs.org/en/latest/what.html) specification , that [includes Django as well](https://docs.djangoproject.com/en/1.8/howto/deployment/wsgi/).

***This article will assume that a Django app has already been created using virtualenv and the task required is to get it running on production server*** <br>. The steps include direct editing of the default virtual hosts file but that is not necessary. 

First  of all, the essentials : apache and mod_wsgi should be installed following the steps of any of the blogs listed above. Now the task remains as to how to serve  the python code and that is where WSGI Directives come in place. The three essential lines to be placed in the default hosts file located at  ***/etc/apache2/sites-available/000-default.conf*** are: <br>

	WSGIDaemonProcess myproject python-path=/home/user/myproject:/home/user/myproject/myprojectenv/lib/python2.7/site-packages<br>
	WSGIProcessGroup myproject<br>
	WSGIScriptAlias / /home/user/myproject/myproject/wsgi.py

The ***first directive*** implies setting up a daemon process named myproject (arbitrary) that will listen to the requests  forwarded by apache. As  is evident, if the python path of the virtualenvironment is not specified, the application will try to run the django app with the system-wide python installation  and that will lead  to  errors. Other than this, you need to provide the path to the Django app, just like the Document  Root  Directive  provided to  Apache in case of PHP or simple HTML pages. The syntax requires a colon between the two directory paths. <br>The ***second directive*** essesntially means that the myproject daemon process belongs to the myproject process group, therefore this particular django app will be executed in the myproject process group.<br> The ***third directive*** simply provides an alias to the wsgi script.

The wsgi script should activate the virtualenvironment while the django app executes and provide the ***application  object***.  As per WSGI secification,  ***an application object used as the entry pointt for requests***. We also need to ensure that our  application and  all the libraries that it  uses are on the python  load path. (eg. from some_module import something,  so some_module should  be on the path.). All of this can be summed up in tthis code piece from [codeship](http://thecodeship.com/deployment/deploy-django-apache-virtualenv-and-mod_wsgi/)

	import os
	import sys
	import site

	# Add the site-packages of the chosen virtualenv to work with
	site.addsitedir('~/.virtualenvs/myprojectenv/local/lib/python2.7/site-packages')

	# Add the app's directory to the PYTHONPATH
	sys.path.append('/home/django_projects/MyProject')
	sys.path.append('/home/django_projects/MyProject/myproject')

	os.environ['DJANGO_SETTINGS_MODULE'] = 'myproject.settings'

	# Activate your virtual env
	activate_env=os.path.expanduser("~/.virtualenvs/myprojectenv/bin/activate_this.py")
	execfile(activate_env, dict(__file__=activate_env))

	import django.core.handlers.wsgi
	application = django.core.handlers.wsgi.WSGIHandler()




With these steps properly executed and [with proper file permissions](http://askubuntu.com/questions/19898/whats-the-simplest-way-to-edit-and-add-files-to-var-www), your django app will start running when you restart  apache.

P.S: My application requires serving media  files only on authentication and so requires intervention by django. In normal cases, it is always advisable to serve  files directly using Apache, the settings for the same are present in the Digital Ocean blog above.

