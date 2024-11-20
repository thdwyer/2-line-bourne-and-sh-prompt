# 2-line-bourne-sh-prompt
Provides a 2 line prompt with the CWD on the top line and the ssh and local host names 
on the actual prompt line

I am often SSHed into my server testing because there is lots of hdd space I can write to
without wearing out an ssd or usb stick.

Most of the time I'm quite a few directories deep and with the standard prompt it's a pain
developing one line for loops because of the length of the CWD string.

To this end I went searching for a 2 line bash prompt, and there are plenty out there, most of
which are way too complex and do heaps more than I was looking to do.

I eventually found one or two that looked like they had promise and I did a bit of fiddling and
combining to get the result I wanted.

The resulting prompt looks like this:

![2LinePrompt](https://github.com/user-attachments/assets/fa1eaf6c-aa63-43e8-9070-531c5f2773e5)

The bottom line changes if you are in a SSH session and looks like this:

![2LinePromptWithSSH](https://github.com/user-attachments/assets/25e236d6-973d-4cd5-a337-187d897e7004)

With the host the SSH session originated from in square brackets on the left and the host logged
into on the right without brackets.  Colours are used effectively so the remote host stands out.

The bottom line is not full of the CWD as thats on the top line between the brackets, so anything
you type at the prompt has room to expand.

To install this, you must be running bash, It doesn't work with dash or zsh, but seems ok with sh.


Installing:  Download the shell script and copy/paste all of into $HOME/.bashrc using xed or your
favourite editor.  Paste the selected code into the file just below the section that says 
"# colored GCC warnings and errors".  That way you won't be in conflict with any of the other
prompt settings.  That is for bash I don't use sh so I don't knowif it has a .shrc file you can use

You will need to do this for every host you login to or the prompt string for the host youssh into
will use it's own .bashrc file.  In addition, because the hostname resolution is done where
you are currently logged in remotely.  In the event the name cannot be resolved, the host between
the square brackets will be the IP adress of the starting host.
