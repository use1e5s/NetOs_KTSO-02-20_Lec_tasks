# Report for program 2

The program creates an array of file descriptors.</br>
After that, the application will check the correctness of the input and output an error message if there is one: </br>
if (argc != 2)</br>
and</br>
if (pipe(pipefd) == -1)</br></br>

Then the program will call fork() of the child process PID of the child process. Next, the application will check the newly received PID. The child element has this ID equal to zero. Next, the parent process writes something: </br>
close(pipefd[0]);</br>
write(pipefd[1], argv[1], strlen(argv[1]));</br>
close(pipefd[1]);</br>
wait(NULL); </br>
exit(EXIT_SUCCESS);</br></br>

And the child reads the data: </br>
if (pid == 0) </br>
{</br>
close(pipefd[1]); </br>
while (read(pipefd[0], & buf, 1) > 0)</br>
write(STDOUT_FILENO, & buf, 1);</br>
write(STDOUT_FILENO, "\n", 1);</br>
close(pipefd[0]);</br>
_exit(EXIT_SUCCESS);</br></br>

In this way, communication between processes is realized using a common channel.</br></br>