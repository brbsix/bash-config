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

   Install
   -----
   
   Copy bash-config to /usr/local/bin and then mark as executable.
   
   ```sudo chmod a+x /usr/local/bin/bash-config```

   Usage
   -----

   When accessing values, the config style is autodetected. When storing a value in a new file, it defaults to Bash-style (i.e. ```PARAMETER=value```).
   
   
   To create the first entry in an ini-style file (i.e. ```PARAMETER = value```):
   
      ```bash-config --ini FILE parameter value```
   
   
   To use a custom separator (i.e. ```PARAMETER:value```) for read and write operations:
   
      ```bash-config --custom : FILE parameter value```
   
   
   To access parameter value:
   
      ```bash-config FILE parameter```


   To delete parameter:
   
      ```bash-config FILE parameter %```
   
   
   To delete config file:
   
      ```bash-config FILE %```
