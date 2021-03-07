# Linux-all-command
All Linux commands and Bash scrpting


Copying fi les
Copying fi les and directories from one location in the fi lesystem to another is a common
practice for system administrators. The cp command provides this feature.
In its most basic form, the cp command uses two parameters — the source object and the
destination object: cp source destination.
When both the source and destination parameters are fi lenames, the cp command
copies the source fi le to a new destination fi le. The new fi le acts like a brand new fi le, with
an updated modifi cation time:
$ cp test_one test_two
$ ls -l test_*
-rw-rw-r-- 1 christine christine 0 May 21 14:35 test_one
-rw-rw-r-- 1 christine christine 0 May 21 15:15 test_two


To create a symbolic link to a fi le, the original fi le must pre-exist. We can then use the ln
command with the -s option to create the symbolic link:
$ ls -l data_file
-rw-rw-r-- 1 christine christine 1092 May 21 17:27 data_file
$
$ ln -s data_file sl_data_file
$
$ ls -l *data_file
-rw-rw-r-- 1 christine christine 1092 May 21 17:27 data_file
lrwxrwxrwx 1 christine christine 9 May 21 17:29 sl_data_file -> data_file




Creating directories
Creating a new directory in Linux is easy — just use the mkdir command:
$ mkdir New_Dir
$ ls -ld New_Dir
drwxrwxr-x 2 christine christine 4096 May 22 09:48 New_Dir





Deleting directories
Removing directories can be tricky, and for good reason. There are lots of opportunities for
bad things to happen when you start deleting directories. The shell tries to protect us from
accidental catastrophes as much as possible. The basic command for removing a directory is
rmdir:
$ touch New_Dir/my_file
$ ls -li New_Dir/
total 0
294561 -rw-rw-r-- 1 christine christine 0 May 22 09:52 my_file
$
$ rmdir New_Dir
rmdir: failed to remove 'New_Dir': Directory not empty

