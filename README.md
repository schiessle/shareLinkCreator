shareLinkCreator
================

This script can be integrated in the Thunar file manager as a "custom
action". It is possible that the program also works with other file managers
which provide similar possibilities, e.g Nautilus. But until now it was only
tested and used with Thunar.

If you configure the "custom action" in Thunar, make sure that you pass the
parameter "%F" to the program. Once the custom action is configured you can
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
"username" and "password" config parameter below

Requirements:
-------------

- curl
- xclip
- zenity
