#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt for start size
    int ss = 0;
    while (ss < 9)
    {
        ss = get_int("Start Size: ");
    }

    // Prompt for end size
    int es = 0;
    while ((es < 9) || (es < ss))
    {
        es = get_int("End Size: ");
    }

    // Calculate number of years until we reach threshold
    int y = 0;
    int np = ss;
    while (np < es)
    {
        int d = np / 3;
        int b = np / 4;
        np = np + b - d;
        y++;
    }

    //Print number of years
    {
        printf("years %i\n", y);
    }
}
