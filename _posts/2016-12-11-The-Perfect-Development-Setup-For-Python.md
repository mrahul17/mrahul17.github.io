---
layout: page
---

I have found the perfect(so far) set of tools for development in python. The first component is *virtual environment*. The second component is [*autoenv*](https://github.com/kennethreitz/autoenv). You create a *.env* file in your project folder and write commands for setting up the environment. For example, when using a virtual environment, we type `source <virtualenv folder>/bin/activate` in the shell. Instead, this is written in the .env file and the shell executes it for us whenever we cd into the project folder (autoenv overrides the cd function to first check for the presence of a .env file, neat!). Other use cases involve starting a server with root located at project folder etc.

That's enough if you are going to be the only developer of the project. Mostly, this is not true and you will want git to ignore it. Adding it to .gitignore is ofcourse an option, but the .env file is not really  a part of the project, rather a productivity tool. Good news! Git has another option to untrack files, without communicating to the remote, by adding the filename to `.git/info/exclude`. I use the following alias to ease the process 

`alias untrackenv="echo '.env' >> .git/info/exclude"`. 

autoenv is not a devil. If you are using a .env file for some other purpose, you can tell this when autoenv asks for confirmation when you cd into the folder for the first time.

