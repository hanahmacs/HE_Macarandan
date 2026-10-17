
#include <stdio.h>

int main() {
    int choice;
    double balance = 500.00;
    double amount;

    do {
        printf("\nBSIT BANK\n");
        printf("Please Select your Transaction\n");
        printf("[1] Balance Inquiry\n");
        printf("[2] Deposit\n");
        printf("[3] Withdraw\n");
        printf("[4] Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("\nYour current balance: P%.2f\n",
                       balance);
                break;

            case 2:
                printf("\nEnter amount to deposit: P");
                if (scanf("%lf", &amount) != 1) {
                    printf("Invalid amount!\n");
                    return 1;
                }

                if (amount <= 0) {
                    printf("Invalid deposit amount!\n");
                } else {
                    balance += amount;

                    printf("P%.2f deposited successfully!\n",
                           amount);
                    printf("Your current balance: P%.2f\n",
                           balance);
                }
                break;

            case 3:
                printf("\nEnter amount to withdraw: P");
                if (scanf("%lf", &amount) != 1) {
                    printf("Invalid amount!\n");
                    return 1;
                }

                if (amount <= 0) {
                    printf("Invalid withdrawal amount!\n");
                } else if (balance - amount < 100.00) {
                    printf("Withdrawal denied!\n");
                    printf("You must maintain at least "
                           "P100.00 in your account.\n");
                } else {
                    balance -= amount;

                    printf("P%.2f withdrawn successfully!\n",
                           amount);
                    printf("Your current balance: P%.2f\n",
                           balance);
                }
                break;

            case 4:
                printf("\nThank you for using BSIT BANK!\n");
                break;

            default:
                printf("\nInvalid choice! Please select "
                       "1 to 4.\n");
        }

    } while (choice != 4);

    return 0;
}
