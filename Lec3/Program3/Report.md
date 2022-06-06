# Report for program 3
Memory allocation for an array of elements of type char: </br>
char * c = (char * ) calloc(100, sizeof(char));</br></br>

Then the application opens the file foo.txt for reading or creating: </br>
int fd = open("foo.txt", O_RDONLY | O_CREAT);</br></br>

After that, the value of the file descriptor is output: </br>
printf("fd = %d/n", fd);.</br> </br>

The application will read 10 bytes from the file and write the received amount of information to the variable sz: </br>
sz = read(fd, c, 10);</br></br>

The program will write terminal zero c[sz] = '\0' to the end of the array; and close the file: </br>
if (close(fd) < 0)</br>
{</br>
perror("close file error:");</br>
exit(1);</br>
}</br></br>