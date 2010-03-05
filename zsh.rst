================
ZSH Notes
================
:Author: `Richard Harding`_
:Repository: `http://github.com/mitechie/zshrc`__
:Description: Scripts to generate virtualenv installs preconfigured for Morpace Pylons applications.

.. __ : http://github.com/mitechie/zshrc

Prompt
======
- Prompt has two parts - left/right
- When the terminal line runs long, right side disappears.
- Using vcs_info you can add in custom prompt details for all major VCS (svn/git/hg/bzr)

::

    [master//zsh_samples N ]%             (rharding@rharding:~/src/zsh_samples/)






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

Working with directories
========================
No cd required
    - /var/www/

auto pushd
    - cd ... ... ... ..
    - dv
    - ~0 / ~1

ignore tab complete
    - /home/rharding/des<tab>

super globbing
    - workit uplift-framework
    - ls -al Ula**/* G php L

Directory alias
    - alog="/var/log/apache2/"
    - more than just a cd alias
    - cd
    - ls alog

Pipe Alias
    - alias -g G='|grep'
    - ls | grep zsh
    - ls G zsh
    - G / L / H / T

Tab Completion is better
    - workit workit
    - git <tab><tab>
        - show detailed help info
    - git show <tab>
        - grouped options
        - ssh <tab>
    - all functions have _xxx check out _git<tab>

Shared History
    - ls /home
    - switch tab
    - (hit enter)
    - up-arrow

Urls:
    - bookmarks http://www.delicious.com/deuce868/zsh
    - github sample configs http://github.com/mitechie/zshrc

