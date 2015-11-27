---
title: "A step-by-step guide: Pelican Netlify CMS"
author: Jimmi Lee
image: null
short_title: The Pelican Netlify CMS Template
description: A short guide on how to set up your very own Pelican Netlify CMS Template.
thumbnail: /uploads/pelicanthumb.png
cmsUserSlug: ""
date: 2015-11-27 
tags: null
---

### **Welcome to Netlify CMS**
While static site generators with CMS capability may be a brand new thing, we *did* cover Netlify CMS previously, with the Jekyll version of our templates [here](https://www.netlify.com/blog/2015/11/6/a-step-by-step-guide-jekyll-netlify-cms) and today we'll take a look at how to set up our pelican-netlify-cms template in much the same manner.

If you merely want to set up Pelican with continous deployment on Netlify, check out [this splendid article](https://www.netlify.com/blog/2015/11/6/a-step-by-step-guide-pelican-on-netlify) by Mr. Aaron Autrand and otherwise keep reading.

### **Geting the Pelican-Netlify-CMS Template**
We'll start by preparing the netlify-git-api CLI tool and then we'll clone the pelican-netlify-cms template repository to our local environment and set it all up.

#### 1. The netlify-git-api CLI tool.
Browse to the [netlify-git-api page](https://github.com/netlify/netlify-git-api/releases) and download the relevant version of the tool.  E.g. as I'm demonstrating this on Ubuntu, I will download the linux.zip file.

Once the download is done, unpack the netlify-git-api executable and place it in your PATH. The methods for doing this are numerous and differ slightly depending on your operating system, but we did as follows on Ubuntu, after using the GUI to unpack the file into our download folder and opening a terminal window (or the Command Prompt in a Microsoft OS):
```
$ cd 'my-downloads'
$ sudo mv netlify-git-api '/usr/local/bin'
```
First we cd into the downloads folder and next we move the netlify-git-api executable to a folder that is in the PATH, so that it can be invoked easily from the terminal.
If you're unsure of where to move the file, you can run the following command to see which directories are in the PATH on your computer:
```
$ echo $PATH
```
*For convenience sake, keep the terminal window/command prompt open throughout this guide.*

#### 2. Fork and Clone the Template.
First we need to fork our own copy of the [pelican-netlify-cms template](https://github.com/netlify-templates/pelican-netlify-cms) and then rename it - we simply named ours Pelican.

Second, we make a local directory to clone our new fork into. Open terminal and go to the location of this directory as seen in the cd command (cd 'your-sites-folde').
The second command below creates the directory we will use for the clone:
```
$ cd '/home/AlcoholiO/Sites'
$ mkdir 'Pelican'
```
To make a local clone we first need to get the remote GitHub URL (it will look like https://github.com/AccountName/RepoName.git or similar) from the Pelican repo we just made- the button looks like this:

![a1_remotegithuburl.png](/uploads/a1_remotegithuburl.png)

Then we open a terminal window to the location of our local repo directory created above and finally we use the following command:
```
$ cd Pelican
$ git clone https://github.com/AlcoholiO/Pelican.git
```
Substitute *https://github.com/AlcoholiO/Pelican.git* with your repository's URL.

#### 3. Setup the Netlify CMS server.
To start the Netlify CMS server, we need to run the following command for each user we wish to add to the system (you will be asked for an email, a name and a password):
```
netlify-git-api users add
```
Alternatively you can create a user, including the information necessary, in a one liner like this:
```
$ netlify-git-api users add -n 'User Name' -e my@email -p mypassword
```
You need to create at least one user, to be able to test the system.