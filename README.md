remotediff - remote diff over rsync
===================================

SYNOPSIS
--------

    $ remotediff [OPTION]... FILES

    Like 'diff' :
    FILES are 'FILE1 FILE2' or 'DIR1 DIR2' or 'DIR FILE...' or 'FILE... DIR'.

    Like 'rsync' :
    FILES can be [[USER@]HOST:]SRC

    But '..' is forbidden in local and remote sources.

    All [OPTION] pass through to 'diff'.


DESCRIPTION
-----------

`remotediff` uses rsync to download remote files to a tmp directory, before
executing `diff` on them locally.

Remote sources 'remote:/SRC1' (absolute) and 'remote:SRC2' (relative) are
passed to 'diff' as '1/remote:/SRC1' and '2/remote:SRC2', but local sources
'/SRC1' (absolute) and 'SRC2' (relative) are passed as '1/SRC1' and '2/SRC2'.

'colordiff' is used if installed and STDOUT is a TTY.


INSTALLATION
------------

To install this module automatically from Git repository :

    cpanm https://github.com/kal247/App-remotediff.git

To install this module manually, run the following commands :

    perl Makefile.PL
    make     
    make test
    make install


SUPPORT AND DOCUMENTATION
-------------------------

After installing, you can find documentation for this module with the
perldoc command :

    perldoc remotediff

You can also look for information at :

- GITHUB

    [https://github.com/kal247/App-remotediff](https://github.com/kal247/App-remotediff)


LICENSE AND COPYRIGHT
---------------------

This software is Copyright (c) 2022 by jul.

This is free software, licensed under:

    The Artistic License 2.0 (GPL Compatible)
