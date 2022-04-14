SYSGIT
======

Git environment wrapper for managing and documenting changes.
Make ''git blame'' on your system.


Initialising
------------

::

  git --git-dir /var/lib/sysgit --work-tree / init
  sys git config status.showuntrackedfiles no

Usage
-----

::

  sys git add /etc/fstab
  sys git commit -m 'add filesystem tab'
  sys git add /etc/shorewall/rules
  sys git status
  sys git blame
  sys tig
  sys bash

  # autocommit changes on /etc/hosts 
  systemctl enable sysgit_commit@-etc-hosts.path

SSH Setup
---------

For having simple commit-ownership setup in sshd::

  #/etc/ssh/sshd_config
  AcceptEnv LANG LC_* GIT_*_NAME GIT_*_EMAIL PTX_*

Set up my ssh to send the git environment variables::

  #~/.ssh/config
  Host *
    SendEnv         GIT_AUTHOR_* GIT_COMMITTER_*


BASH Setup
----------

::

  #~/.bashrc
  export GIT_AUTHOR_NAME="Björn Lässig"
  export GIT_COMMITTER_NAME="Björn Lässig"
  export GIT_AUTHOR_EMAIL="b.laessig@pengutronix.de"
  export GIT_COMMITTER_EMAIL="b.laessig@pengutronix.de"


Whats missing
-------------

* ansible module
