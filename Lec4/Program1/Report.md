# Report for program 1

At the very beginning, the program receives a signal from the user and processes it.</br>
Then a global counter variable is set: </br>
int counter = 0;</br></br>

Also in the program there are two processing functions - handler1: </br>
void handler1(int sig)</br>
{</br>
counter++;</br>
printf("counter = %d\n", counter);</br>
/* Flushes the printed string to stdout */</br>
fflush(stdout);</br>
kill(pid, SIGUSR1);</br>
}</br></br>

And the handler2 function: </br>
void handler2(int sig)</br>
{</br>
counter += 3;</br>
printf("counter = %d\n", counter);</br>
exit(0);</br>
}</br>

Processing: The program binds the first processing function to the current process.</br>
Further, if the process turns out to be a child, the handler2 function will process the signal.</br></br>