---
published: true
title: Amazing things I never knew I could do (aka IPython magic)
layout: post
---
## Edit an object code

    In [1]: import requests
    In [2]: %edit -x requests.Session

![screenshot-from-shell](http://i.imgur.com/CeiDPcAl.png)
[Imgur]()

By default (without `-x` param) IPython will execute the code after exiting.
See the [edit magic documentation](https://ipython.org/ipython-doc/3/interactive/magics.html#magic-edit)

## wrap code in pdb or jump into postmortem

    In [1]: def foo():
       ...:         raise Exception("bar")
       ...: %debug foo()
       ...:
    NOTE: Enter 'c' at the ipdb>  prompt to continue execution.
    > <string>(1)<module>()

    ipdb> c
    ---------------------------------------------------------------------------
    Exception                                 Traceback (most recent call last)
    <ipython-input-14-5b0cb4720e0e> in foo()
          1 def foo():
    ----> 2         raise Exception("bar")
          3 get_ipython().magic('debug foo()')
          4

    Exception: bar


Are you amazed yet? See [debug magic documentation](https://ipython.org/ipython-doc/3/interactive/magics.html#magic-debug).

## Persist aliases, macros and namespace variables

    In [1]: import logging; logging.basicConfig(); logging.getLogger().setLevel(0)

    In [2]: %hist -n
       1: import logging; logging.basicConfig(); logging.getLogger().setLevel(0)
       2: %hist -n

    In [3]: %macro console 1
    Macro `console` created. To execute, type its name (without quotes).
    === Macro contents: ===
    import logging; logging.basicConfig(); logging.getLogger().setLevel(0)

    In [4]: %store console
    Stored 'console' (Macro)

Now, you can restore stored macros with

    In [1]: %store -r

Alternatively, you may toggle autorestore in your profile (e.g ~/.ipython/profile_default/ipython_config.py):

    c.StoreMagic.autorestore = True
