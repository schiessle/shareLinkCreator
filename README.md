Share Link Creator
==================

This script can be integrated in the Thunar file manager as a "custom
action". The program should also works with other file managers which provide
similar possibilities to integrate shell scripts. I developed and used this
script with Thunar only but I got some feedback that it also works nicely with
Dolphin and Nautilus.

This script will also work with Nemo (used with Linux Mint, etc), instructions on how to use with nemo are listed below.

If you configure the "custom action" in Thunar, make sure to pass the paths of
all selected files to the program using the "%F" parameter. The program expects
the absolute path to the files.  Once the custom action is configured you can
execute the program from the right-click context menu. The program works for
all file types and also for directories. Once the script gets executed it will
first upload the files/directories to your ownCloud and afterwards it will
generate a public link to access them. The link will be copied directly to your
clipboard and a dialog will inform you about the URL. If you uploaded a single
file or directory than the file/directory will be created directly below your
"uploadTarget" as defined below. If you selected multiple files, than the
programm will group them together in a directory named with the current
timestamp.

Before you can use the program you need to adjust at least the "baseURL",
"username" and "password" config parametes at the top of the script. If you
keep "username" and/or "password" empty a dialog will show up and ask for the
credentials.

Requirements:
-------------

- curl
- xclip
- zenity

Installing with Nemo (Linux Mint)
--

You will need to copy the shareLinkCreator.nemo_action to:

~/.local/share/nemo/actions/

Next edit the file, and replace

    Exec=/path/to/shareLinkCreator/shareLinkCreator %F

With the full path to the shareLinkCreator file, and voila!  Make sure you have configured the shareLinkCreator file as instructed above.
