# CSOC-INFOSEC



## Week 0


###  TASK 1 Over The Wire [bandit] (I have solved more lvls but writeup is pending will soon compelete it)

#### level 0 - entering in level 0 is easy as it just uses ssh to login to the server with username,adderess,port and password.

#### level 1 - in this lvl in its given that pass is given in the readme  file that is in home directory so its just using ls and cd command to find it.(pass=ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If)

#### level 2 -263JGJPfgU6LtdEvgfWU1XP5yac29mFx

### level 3- -MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx


### level 4-2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

### level 5-4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

### level 6-HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

### level 7-morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

### level 8- dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc


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

#### To do list(Sigle User)
In python
```
import os

FILE_NAME = "file.txt"

def add_task():
    task = input("enter a new task: ").strip()
    if task:
        with open(FILE_NAME, "a") as file:
            file.write(task + "\n")
        print("task added")
    else:
        print("empty task not added.")

def view_tasks():
    if not os.path.exists(FILE_NAME):
        print("No tasks found.")
        return

    print("\nyour to-do List:")
    with open(FILE_NAME, "r") as file:
        tasks = file.readlines()

    if tasks:
        for idx, task in enumerate(tasks, 1):
            print(f"{idx}. {task.strip()}")
    else:
        print("No tasks found.")

def clear_tasks():
    open(FILE_NAME, "w").close()
    print("All tasks cleared.")

def main():
    while True:
        print("\n==== To-Do List Menu ====")
        print("1. View Tasks")
        print("2. Add Task")
        print("3. Clear All Tasks")
        print("4. Exit")

        choice = input("Enter choice: ").strip()

        if choice == "1":
            view_tasks()
        elif choice == "2":
            add_task()
        elif choice == "3":
            clear_tasks()
        elif choice == "4":
            break
        else:
            print("invalid try again.")

main()
```




