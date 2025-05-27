# Narcissistic-Numbers

#include <stdio.h>
#include <math.h>

void power(int *array, int size)
{
    for(int i = 0; i < size; i++)
    {
        array[i] = pow(array[i], size);
    }
}

void numberToArray(int *array, int size, int x)
{
    for(int i = size - 1; i >= 0; i--)
    {
        array[i] = x % 10;
        x /= 10;
    }
}

int sizeCalculator(int x)
{
    int size = 0;
    if(x == 0)
    {
        return 1;
    }
    while(x > 0)
    {
        x /= 10;
        size++;
    }
    return size;
}

int main(void)
{
    int x;
    int size;
    int num = 0;

    printf("Enter a number: ");
    scanf("%d", &x);

    size = sizeCalculator(x);

    printf("size: %d\n", size);

    int array[size];

    numberToArray(array, size, x);

    printf("Seperated numbers:\n");
    for(int i = 0; i < size; i++)
    {
        printf("%d ", array[i]);
    }
    printf("\n");

    power(array, size);

    printf("Seperated numbers to the power of two:\n");
    for(int i = 0; i < size; i++)
    {
        printf("%d ", array[i]);
    }
    printf("\n");

    for(int i = 0; i < size; i++)
    {
        num = num + array[i];
    }
    
    printf("Final number is: %d\n", num);

    if(x == num)
    {
        printf("%d is a narcissistic number", x);
    }
    else
    {
        printf("%d is not a narcissistic number", x);
    }

    return 0;
}
