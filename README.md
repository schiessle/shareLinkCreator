Share Link Creator
==================

Provides the ability to upload a file to Nextcloud via a supported file manager
and receive a link to the uploaded file which can then be emailed or shared in
another way.

This script can be integrated in the Thunar file manager as a "custom
action". The program should also works with other file managers which provide
similar possibilities to integrate shell scripts. I developed and used this
script with Thunar only but I got some feedback that it also works nicely with
Dolphin, Nautilus and Nemo.

The program expects the absolute path to the files.  Once the custom action is
configured you can execute the program from the right-click context menu. The
program works for all file types and also for directories. Once the script gets
executed it will first upload the files/directories to your Nextcloud and
afterwards it will generate a public link to access them. The link will be
copied directly to your clipboard and a dialog will inform you about the
URL. If you uploaded a single file or directory than the file/directory will be
created directly below your "uploadTarget" as defined below. If you selected
multiple files, than the programm will group them together in a directory named
with the current timestamp.

Requirements
------------

- curl
- xclip
- zenity

Configuration
-------------

Before you can use the program you need to adjust at least the "baseURL" at
"config.sample" and rename the file to "config". If you keep "username" and/or
"password" empty a dialog will show up and ask for the credentials.


Installing with Thunar (Xfce)
-----------------------------

Start Thunar and go to "Edit->Configure Custom Actions...". Here you can add a
action to execute the shareLinkCreator. Make sure to pass the "%F" parameter
(paths to all selected files) to the program. Under "Appearance Conditions" you
can enable all file types.


Installing with Nemo (Linux Mint / Cinnamon)
--------------------------------------------

You will need to copy the shareLinkCreator.nemo_action to:

    ~/.local/share/nemo/actions/

Next edit the file, and replace

    Exec=/path/to/shareLinkCreator/shareLinkCreator %F

With the full path to the shareLinkCreator file, and voila!  Make sure you have
configured the shareLinkCreator file as instructed above.
