---
published: true
title: Split big git repository into seperate repo
layout: post
---
# Preface
Occasionally, you'll work on a repository which contains multiple reusable packages.

This time, you might feel that one of these sub-directories should be it's own repository. Obviously you could simply copy the repo content into a new bare repo, and start "from scratch"; but what if you want to retain the change history?

Well, apparently it's real easy!

# Solution

Use `git filter-branch`

    $ cd /home/pavel/myapps 
    $ tree
    .
    ├── django-adminactions
    │   ├── AUTHORS
    │   ├── ...
    ├── django-cms-smartsnippets
    │   ├── LICENSE
    │   ├── ...
    ├── django_feed_imports
    │   ├── MANIFEST.in
    │   ├── README.rst
    │   ├── __init__.py
    │   ├── feed_imports
    │   │   ├── __init__.py
    │   │   ├── admin.py
    │   │   ├── models.py
    │   │   ├── templatetags
    │   │   │   ├── __init__.py
    │   │   │   └── feed_items.py
    │   │   ├── urls.py
    │   │   └── utils.py
    │   └── setup.py

    $ cd /home/pavel/
    $ git clone /home/pavel/myapps django_feed_imports
    $ cd django_feed_imports/
    $ git remote rm origin
    $ git filter-branch --subdirectory-filter django_feed_imports -- --all
    $ tree
    .
    ├── MANIFEST.in
    ├── README.rst
    ├── __init__.py
    ├── feed_imports
    │   ├── __init__.py
    │   ├── admin.py
    │   ├── models.py
    │   ├── templatetags
    │   │   ├── __init__.py
    │   │   └── feed_items.py
    │   ├── urls.py
    │   └── utils.py
    └── setup.py