# Report for program 3

First, the program creates a handle and a channel with access rights for everyone: </br>
int fd; </br>
int len;</br>
char buf[BUFSIZE];</br>
if (mkfifo(NAMEDPIPE_NAME, 0777))</br>
{ </br>
perror("mkfifo");</br>
return 1;</br>
}</br>
</br></br>

After that, an infinite loop is started in which the application listens to it: </br>
do {</br>
memset(buf, '\0', BUFSIZE);</br>
if ((len = read(fd, buf, BUFSIZE - 1)) <= 0) </br>
{</br>
error("read error");</br>
close(fd);</br>
remove(NAMEDPIPE_NAME);</br>
return 0;</br>
}</br>
printf("Incoming message (%d): %s\n", len, buf);</br>
} while (1);</br></br>

If the program received the message: </br>
if ((len = read(fd, buf, BUFSIZE - 1)) <= 0)</ br>
The number of characters is output (taking into account the terminal zero) and the text itself.</br></br>