#include<iostream>
#include<cstdlib>
#include<ctime>
using namespace std;

int main() {
    cout << "\n\t\t_Welcome to the Number Guessing Game_\n" << endl;
    cout << "\n\t\t--> You will have to guess a number between 2 to 101.";
    cout << "\n\t\t--> Lets start playing and Best of Luck." << endl;

    srand(time(0));
    int randNumber = (rand() % 100) + 1;

    cout << "\n^^*You will have total 5 chances to guess the correct number.*^^\n";
    int chanceLeft = 5;
    int playerInput;

    for (int i = 1; i <= 5; i++) {
        cout << "\n=> Enter the Number: ";
        cin >> playerInput;

        if (playerInput == randNumber) {
            cout << "\nCongrats!! You have successfully guessed the right number\n";
            cout << "\nThanks for playing. Have a nice Day";
            break;
        } else {
            if (playerInput > randNumber) {
                cout << "\nInsert a Smaller Number. Try Again" << endl;
            } else {
                cout << "\n[ Insert a Larger Number. Try Again ]" << endl;
            }
        }

        chanceLeft--;
        cout << "\n( Chances Left to guess the Random Number: " << chanceLeft << " )" << endl;

        if (chanceLeft == 0) {
            cout << "\nSorry your chance has been finished to guess the random number\n" << endl;
            cout << "The random Number was: " << randNumber << endl;
            cout << "Thanks for playing. Have a nice day.";
        }
    }

    cout << "\n";
    return 0;
}
