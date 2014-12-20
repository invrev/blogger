
@SHELL

command history search
Ctrl-r 

Ctrl-w to kill the last word, and Ctrl-u to kill the line.

Ctrl-a go to begining


#Get the file information in decimal format
stat -c/-f '%A %a %n' /home/test_File



Use hash tags to organize your bash history.

We use hash tags all over in Twitter, Hashtags are excellent for discovering and tagging long text. 

And #HashTags can be made our workflows more productive! 

Note:
# in shell means a comment. 

We normally type very long commands in our bash. 

Trick: Just append a hash tag in every command you type at the end.

And later search for the hash tag in reverse-i-search (Ctrl + R).
Since, anything that follows # is treated as a comment in Bash, the text is silently ignored after #

eg1: 
Say I run this command on my Bash Shell
$ tar xzvf filename #untar

Now, just Ctrl + R, and type untar and you get the command!



ssh <remote user>@<remote host> mkdir -p .ssh && cat .ssh/id_rsa.pub | ssh <remote user>@<remote host> 'cat >> .ssh/authorized_keys'

