# CSOC-INFOSEC



## Week 1


###  TASK 1 Over The Wire [bandit]

#### level 0 - entering in level 0 is easy as it just uses ssh to login to the server with username,adderess,port and password.

#### level 1 - in this lvl in its given that pass is given in the readme  file that is in home directory so its just using ls and cd command to find it.(pass=ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If)

#### level 2 -



### TASK 2 

#### Russian roulette
In C 

```

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int arr[6] = {0};  //  6-chamber revolver
    int bp; // bullet position
    int players, cp = 0;// cp = currentPlayer
    char input;

    srand(time(NULL)); // uses current time to feed the randowm seed gen which gives random value

    printf(" Russian Roulette \n");
    printf("Enter number of players (2-6): ");
    scanf("%d", &players);

    if (players < 2 || players > 6) {
        printf("NOT A VALID NUMBER OF PLAYERS!!!!\n");
        return 1;
    }

    
    bp = rand() % 6; // gives a random no. b/w 1-6

    printf(" Starting  the game\n");

    int flag=1;

    while (flag) {
        printf("\nPlayer %d's turn. Press Enter to pull the trigger...", cp + 1);
        getchar();  // consume newline 
        getchar();  // for Enter

        int triggerPull = rand() % 6;
        printf("Chamber position: %d\n", triggerPull);

        if (triggerPull == bp) {
            printf("Player %d is out.\n", cp + 1);
            flag=0;
        } else {
            printf("Player %d survives.\n", cp + 1);
            cp = (cp + 1) % players;
        }
    }

    printf("\nGame over.\n");
    return 0;
}




```

#### Sorting Routine
In C

```
#include <stdio.h>

void bubbleSort(int arr[], int n) {
    int temp;
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

int main() {

    int n;
    printf("enter the size of array");
    scanf("%d",&n);
    int arr[n];

    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    
    bubbleSort(arr, n);
    printf("Sorted array: \n");
    printArray(arr, n);
    return 0;
}

```




