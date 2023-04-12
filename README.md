# MOMO-PROJECT
Class project
#include <iostream>
#include <string>
using namespace std;

int main() {
    // default pin and balance
    int default_pin = 0000;
    int default_balance = 1000;

    // variables for user input and account information
    int pin, balance, recipient_number, amount;
    int attempts = 0;
    string option;

    // prompt user to enter pin
    cout << "Enter your pin: ";
    cin >> pin;

    // check if pin is correct
    if (pin == default_pin) {
        cout << "Authentication successful." << endl;
        balance = default_balance;
        // display options for user
        while (option != "exit") {
            cout << "Select an option:" << endl;
            cout << "1. Reset/change pin" << endl;
            cout << "2. Check balance" << endl;
            cout << "3. Send money" << endl;
            cout << "4. Exit" << endl;
            cin >> option;

            // option 1: reset/change pin
            if (option == "1") {
                cout << "Enter new pin: ";
                cin >> default_pin;
                cout << "Pin changed successfully." << endl;
            }

            // option 2: check balance
            else if (option == "2") {
                cout << "Your balance is: " << balance << endl;
            }

            // option 3: send money
            else if (option == "3") {
                cout << "Enter recipient's phone number: ";
                cin >> recipient_number;
                cout << "Enter amount to send: ";
                cin >> amount;
                if (amount <= balance) {
                    balance -= amount;
                    cout << "Transaction successful. Your new balance is: " << balance << endl;
                }
                else {
                    cout << "Transaction failed. Insufficient funds." << endl;
                }
            }

            // option 4: exit
            else if (option == "4") {
                cout << "Exiting program." << endl;
                break;
            }

            // invalid option
            else {
                cout << "Invalid option. Please try again." << endl;
            }
        }
    }
    // incorrect pin
    else {
        attempts++;
        while (attempts < 3) {
            cout << "Incorrect pin. Please try again." << endl;
            cout << "Enter your pin: ";
            cin >> pin;
            if (pin == default_pin) {
                cout << "Authentication successful." << endl;
                balance = default_balance;
                // display options for user
                while (option != "exit") {
                    cout << "Select an option:" << endl;
                    cout << "1. Reset/change pin" << endl;
                    cout << "2. Check balance" << endl;
                    cout << "3. Send money" << endl;
                    cout << "4. Exit" << endl;
                    cin >> option;

                    // option 1: reset/change pin
                    if (option == "1") {
                        cout << "Enter new pin: ";
                        cin >> default_pin;
                        cout << "Pin changed successfully." << endl;
                    }

                    // option 2: check balance
                    else if (option == "2") {
                        cout << "Your balance is: " << balance << endl;
                    }

                    // option 3: send money
                    else if (option == "3") {
                        cout << "Enter recipient's phone number: ";
                        cin >> recipient_number
