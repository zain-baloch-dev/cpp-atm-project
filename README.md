```cpp

#include <iostream>
using namespace std;

int main()
{
    float balance = 100000, amount;
    int choice;
    char again;

    // PIN variables
    int stored_pin = 1234; // Aapka default PIN
    int input_pin, attempts = 0;

    // PIN Validation (3 attempts allow karte hain)
    while (attempts < 3)
    {
        cout << "Enter your 4-digit PIN: ";
        cin >> input_pin;
        if (input_pin == stored_pin)
        {
            cout << " ACCESS GRANTED " << endl;
            break;
        }
        else
        {
            attempts++;
            cout << "Incorrect PIN. Attempts left: " << (3 - attempts) << endl;
        }

        if (attempts == 3)
        {
            cout << "Too many incorrect attempts. Your card is blocked!" << endl;
            return 0; // Program yahin khatam ho jayega
        }
    }

    do
    {
        cout << " ***WELCOME TO ATM*** " << endl;
        cout << " ATM MENU " << endl;

        cout << " 1.BALANCE INQUIRY " << endl;
        cout << " 2.CASH WITHDRAWAL " << endl;
        cout << " 3.CASH DEPOSIT " << endl;
        cout << " 4.EXIT " << endl;
        cout << " choice an option " << endl;
        cin >> choice;

        switch (choice)
        {
        case 1:
            cout << " Your balance is " << balance << endl;
            break;
        case 2:
            cout << " Enter amount for withdrawal " << endl;
            cin >> amount;
            if (amount < balance)
            {
                balance -= amount;
                cout << " withdrawn amount is: " << amount << "pkr" << endl;
                cout << " your remaning balance is " << balance << "pkr" << endl;
            }

            else
            {
                cout << " insufficient balance " << endl;
            }
            break;

        case 3:
            int deposit;
            cout << " Enter amount for cash deposit " << endl;
            cin >> deposit;
            balance += deposit;
            cout << " cash deposit amount is  " << deposit << "pkr" << endl;
            cout << " new balance is " << balance << "pkr" << endl;
            break;

        case 4:
            cout << " ***Thank you for using this ATM*** " << endl;
            return 0;

        default:
            cout << " invalid choice " << endl;
        }

        cout << "\nDo you want to perform another transction (y/n): ";
        cin >> again;

    } while (again == 'y' || again == 'y');

    cout << " ***Thank you for using this ATM*** " << endl;

    return 0;
}


```
