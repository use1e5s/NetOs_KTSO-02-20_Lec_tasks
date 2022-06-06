# Report for Program1
Specifying the length of the array: </br>
printf("Enter length of array: ");</br>
scanf("%d", &length);</br></br>

Allocation of memory for an array. If no memory is allocated, the malloc function returns NULL: </br>
if ((array = (int * ) malloc(length * sizeof(int))) != NULL)</br></br>

If everything went without errors, the program will clear the allocated memory: </br>
if (array != NULL)</br>
{</br>
free(array);</br>
}</br></br>

