---
layout: post
title: "iPython notebooks and OS X Mountain Lion"
date: 2013-01-12 21:45
comments: true
categories: 
---

To get [iPython notebooks](http://ipython.org/ipython-doc/dev/interactive/htmlnotebook.html) running under OS X Mountain Lion, the first thing to install is install Chris Fonnesbeck's excellent [Scipy Superpack](http://fonnesbeck.github.com/ScipySuperpack/).

Once that was installed, I also had to install a few [dependencies](http://ipython.org/ipython-doc/dev/install/install.html#dependencies-for-the-ipython-html-notebook) before the notebooks worked:

    sudo easy_install ipython[zmq]
    sudo easy_install Tornado
    sudo easy_install Jinja2


