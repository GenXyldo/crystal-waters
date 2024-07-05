#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

// Function to generate a random number of water crystals
int generateCrystals() {
    return rand() % 10 + 1; // Generates a number between 1 and 10
}

// Function to display the current score
void displayScore(int score) {
    cout << "You have collected " << score << " water crystals so far!" << endl;
}

int main() {
    srand(time(0)); // Seed for random number generation

    int totalCrystals = 0;
    char choice;

    cout << "Welcome to the Crystal Waters game!" << endl;

    while (true) {
        cout << "Press 'c' to collect water crystals or 'q' to quit: ";
        cin >> choice;

        if (choice == 'q') {
            break;
        } else if (choice == 'c') {
            int crystals = generateCrystals();
            totalCrystals += crystals;
            cout << "You collected " << crystals << " water crystals!" << endl;
            displayScore(totalCrystals);
        } else {
            cout << "Invalid choice. Please try again." << endl;
        }
    }

    cout << "Game over! You collected a total of " << totalCrystals << " water crystals." << endl;
    return 0;
}
