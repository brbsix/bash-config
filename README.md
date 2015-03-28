# bash-config

Bash script to interact with configuration files. Great for easily implementing basic config files in all of your Android, Linux, or OSX shell scripts.

Features
--------

* read/write/delete parameters with values
* create and delete config files
* autodetection of config style (between Bash and ini)
* options for different styles of config files
    * Bash-style
    * Window's ini-style
    * use custom delimeter

Linux Installation
------------------

To install bash-config on Linux:

    sudo install bash-config /usr/local/bin

Android Installation
--------------------

This script was originally written for Bash but now supports Android's default shell mksh as well.

The only external tools used by bash-config are grep and sed. If you are missing either of these then you should install busybox.

Assuming you can download or otherwise transfer bash-config onto your phone, here are the installation instructions:

    su
    cp bash-config /data/local/bin
    sed -i 's:#!/bin/bash:#!/system/bin/mksh:' /data/local/bin/bash-config  # update the shebang for Android's default shell
    chmod 0755 /data/local/bin/bash-config

*NOTE: You may need to add /data/local/bin to your PATH. This involves editing your shell's rc file. If you are using the default mksh shell, it is located at /system/etc/mkshrc. For Bash, it is most likely at /system/etc/bash/bashrc. Append the following to the end of the file:*

    export PATH="$PATH:/data/local/bin"

Usage
-----

When accessing values, the config style is autodetected. When storing a value in a new file, it defaults to Bash-style (i.e. `PARAMETER=value`).

To create the first entry in an ini-style file (i.e. `PARAMETER = value`):

    bash-config --ini FILE parameter value

To use a custom separator (i.e. `PARAMETER:value`) for read and write operations:

    bash-config --custom : FILE parameter value

To access parameter value:

    bash-config FILE parameter

To delete parameter:

    bash-config FILE parameter %

To delete config file:

    bash-config FILE %

License
-------

Copyright (c) 2015 Six (brbsix@gmail.com).

Licensed under the GPLv3 license.
