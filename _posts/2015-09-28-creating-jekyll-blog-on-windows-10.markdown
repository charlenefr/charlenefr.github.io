---
layout: post
title:  "My Problems with Installing Jekyll on Windows 10"
date:   2015-09-28 16:17:00
categories: jekyll
---
I used [this helpful article][tod-thomson] to install Jekyll to use in GitHub Pages. There were several problems that weren't mentioned there that I'll mention now, and hopefully it can be helpful to other people who might have the same problem.

Installing Prerequisites
===========================
Installing Node.js
---------------------------
###Adding Node.js to path
Just make sure that when you Install Node.js "Add to Path" is selected in the installation process :)
Installing Python
---------------------------
I have Python 3.1 and Python 2.7 installed on my laptop (x64). I uninstalled Python 3.1 with no problem. I tried to run `python -m pip install Pygments` on the command prompt but then an error popped up:

>'python' is not recognized as an internal or external command

I had no idea what it meant for the longest time, and I was uninstalling and re-installing Python 2.7 (which came up with another problem, but I'll save that for another post). But basically, this means that you haven't added Python to the path yet. Here's a way to do this:

###Finding the Path
1. Right-click the Windows icon on the taskbar.
2. Select 'System'.
3. Select 'Advanced System Settings' which is on the left.
3. If you're not on the main account of your PC (which I wasn't), it will ask you for a password or a pin.
4. On the Advanced Tab, select 'Environment Variables', which will be right above the 'OK' Button.
5. Select the 'PATH' on the 'User Variables for...' and click Edit.
###Adding Python to the Path
1. Add this code at the end of the path. **DON'T DELETE ANYTHING FROM THE PATH**. Just add `;c:\python27/` at the end. 
2. Click OK.
3. Restart the shell and type `python -m pip install Pygments` on the command prompt and it should now work.

Installing Jekyll
===============================
It took me ages to figure out that when Tod said `jekyll new .` it had a dot at the end. It was giving me an error at the terminal where it was asking me to find a path (and at that point I wanted to bang my head on the desk because I just finished getting Python to work). Be aware that there's a dot, and remember to include that dot.
Pygments vs. Rouge
-------------------------------
On the `_config.yml` file, highlighter wasn't even included, so just feel free to add `highlighter: pygments` on the file yourself.

Hosting on GitHub Pages
===============================
I will be assuming a few things:
1. You haven't yet cloned the repository to your Computer
2. You have GitHub Desktop and you are logged in on it.

Here was what I did to get Jekyll on my GitHub Page:
1. On GitHub Desktop, clone the repository. If you're logged in, you can just select it.
2. Using Git Bash, redirect to the directory where you cloned your repository. For me, it was on `Documents/GitHub/`.
3. Follow his instructions on the BlogTest and you should be fine :)

Update "All the Things!"
==============================
Just be aware that when he says the updating will take a long time, *it will take a long time*. But you need to look at it every few minutes because it might ask you to overwrite gems, and you'll need to answer it. :)



[tod-thomson]: http://todthomson.com/2015/01/11/jekyll-on-windows/