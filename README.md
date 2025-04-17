#include <stdio.h>
#define ROWS 5
#define COLS 4

void displaySeats(int seats[ROWS][COLS]){
    printf("\nBus Seat Layout (0=Available, 1=Booked):\n");
    for (int i=0; i<ROWS; i++){
        printf("Row %d:",i+1);
        for(int j = 0; j<COLS; j++){
            printf("%d",seats[i][j]);
        }
        printf("\n");
        }
    }
    void reserveSeat(int seats[ROWS][COLS]){
        int row, col;
        printf("\nEnter row number (1-%d):",ROWS);
        scanf("%d",&row);
        printf("Enter seat number in the row(1-%d):",COLS);
        scanf("%d",&col);
        if(row<1||row>ROWS||col<1||col>COLS){
            printf("Invalid seat position! Try again.\n");
            return;
        }
        if (seats[row-1][col-1]==0){
            seats[row-1][col-1]=1;
            printf("Seat successfully reserved.\n");
        }else{
            printf("Seat is alread booked. Choose another one .\n");
        }
    }
    int main(){
        int seats[ROWS][COLS]={0};
        int choice;
        do{
            printf("\n---Bus Seat Reservation Menu ---\n");
            printf("1.View Seats\n");
            printf("2.Reserve Seat\n");
            printf("3.Exit\n");
            printf("Enter your choice:");
            scanf("%d",&choice);
            switch (choice){
                case 1:
                displaySeats(seats);
                break;
                case 2:
                reserveSeat(seats);
                break;
                case 3:
                printf("Exiting System. Thank you!\n");
                break;
                default:
                printf("Invalid choice! Please try again.\n");
            }
        }while (choice !=3);
        return 0;
    };
            
