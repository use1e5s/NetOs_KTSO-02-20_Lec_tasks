# Report for program 4
First, the program calls the fork() function, which creates a child process: </br>
int pid = fork();</br></br>

Then the application will output the PID of the processes in which it is located: </br>
printf("my pid =%i, returned pid =%i\n", getpid(), pid);</br></br>