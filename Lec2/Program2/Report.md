# Report for Prog2


Указание длины массива.
printf("Enter length of array: ");
scanf("%d", &length);

Выделение памяти для массива. Если память не выделилась, функция malloc вернёт значение NULL.
if ((array = (int * ) malloc(length * sizeof(int))) != NULL)

После этого идет вывод количество байтов, которое было выделено.
printf("Allocated %lu bytes\n", length * sizeof(*array));

Если всё прошло без ошибок, программа очистит выделенную память.
if (array != NULL)
{
free(array);
}


