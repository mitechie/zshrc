================
ZSH Notes
================
:Author: `Richard Harding`_
:Contact: mitechie (twitter/identica)
:Repository: `http://github.com/mitechie/zshrc`__
:Bookmarks: http://www.delicious.com/deuce868/zsh

.. __ : http://github.com/mitechie/zshrc
.. _Richard Harding : rharding@mitechie.com


Prompt
======
::

    [master//zsh_samples N ]%             (rharding@rharding:~/src/zsh_samples/)

- Prompt has two parts - left/right
- When the terminal line runs long, right side disappears.
- Using vcs_info you can add in custom prompt details for all major VCS (svn/git/hg/bzr)


Vim Mode
========
  - ``esc`` : enter command mode 
    
    - I use mapped to ``jj``

  - w/b : forward/back word in editing prompt
  - cw/dw : change current word/delete word
  - ``f /`` : move cursor forward to first instance of forward slash
  - !!:s/XX/YY : Run last command, but replace XX with YY
  - / and ? : searching the command history
    - n/N : next/prev result
  - ``v`` : edit current command line in vim


Vim Edit Sample
===============
::

    for i in $(seq 1 10); do time wget -t1 -O/dev/null \
    'http://www.predictadxml.com/ads/?pid=5152&cs=872&keyword=cash&ref=http%3a%2f%2fwww.exampledomain.com&adult=0&ua=Mozilla%2f5.0+(Windows%3b+U%3b+Windows+NT+5.1%3b+en-US%3b+rv%3a1.9.0.3)+Gecko%2f2008092417+Firefox%2f3.0.3&f=1&subid=1&count=2&ip=194.117.97.95'; \
    done 2>&1 | grep real



Working with directories
========================
- No cd required

::

    $ /var/www/

- auto pushd

::

    $ cd /var/log
    $ cd /var/www
    $ cd /etc/apache2
    $ dv
    $ ~1


- ignore tab complete

::

    $ /home/rharding/flos<tab>
    $ ~/flos<tab>

- super globbing

::

    $ workit hotalert
    $ ls -al qsat**/* G mako L


Aliases
========

- Directory alias
    
  - more than an alias for a cd command, usable as parameter to other commands

::

    $ alias -g alog="/var/log/apache2/"
    $ alog
    $ ls alog


- Pipe Alias

  - uses ``-g`` flag

::

    $ workit zsh_samples
    $ alias -g G='|grep'
    $ ls | grep zsh
    $ ls G zsh


Pipe Aliases
==============
- G : grep
- L : less
- H : head
- T : tail
- S : sort
- W : wc -l
- V : vim
- A : ack-grep


Extension Aliases
=================
Opens files with that extension in that application

- uses ``-s`` flag

::

    $ alias -s php=gvim
    $ alias -s pdf=xpdf
    $ fabfile.py
    $ Python_Testing_Beginner's_Guide.pdf


Tab Completion is better
========================
::

    $ workit workit

- Shows all of the possible commands with help text

:: 

    $ git <tab><tab>


- Show grouped options

:: 

    $ git show <tab>
    $ ssh <tab>

- Provded by completion functions, small and easy to do

::

    $ __git<tab>


Shared History
===============
::

    $ ls /home

- switch to already running tab

:: 

    $ <enter>
    $ <up-arrow>


Workit
======
- http://github.com/mitechie/workit

Assists in quickly working on various src/text projects you might have.

- Provides a postactivate and postdeactivate file

  - perform actions (update vim ctags)
  - set env variables (build paths)
  - start/stop services (mysql/postgres/apache)
  - define shortcuts used i.e. (qunit)


Workit Example
==============
::

    $ workit tadmin
    $ vi postactivate

::

    $ workit zsh_samples
    $ workit <tab>
    $ workit pyvim
    $ workit hotalert


Workit Notes
=============
Currently only works in zsh, needs some bash love. Completion scripts
::

    compctl -g "`show_workit_projects`" workit

ZSH has higher level arrays that bash doesn't. Need to translate.

