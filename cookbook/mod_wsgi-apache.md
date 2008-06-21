---
layout: default
title: Webpy + Apache with mod_wsgi
---

# Webpy + Apache with mod_wsgi

The following steps was tested on Apache-2.2.3 (Red Hat Enterprise Linux 5.2, x86_64), mod_wsgi-2.0.

Note:

* You may replace 'appname' with your own project name.
* You may replace code.py with your own file name.
* /var/www/webpy-app found below refers to the path to the directory contains your code.py
* /var/www/webpy-app/code.py is the full path to your python file

Steps:
* Download and install mod_wsgi from its website: http://code.google.com/p/modwsgi/. It will install a '.so' module in /usr/lib64/httpd/modules/.
* Setup Apache to load mod_wsgi module in httpd.conf:

    LoadModule wsgi_module modules/mod_wsgi.so

* Setup Apache to 

    WSGIScriptAlias /appname /var/www/webpy-app/code.py

    <Directory /var/www/webpy-app/>
        Order deny,allow
        Allow from all
    </Directory>