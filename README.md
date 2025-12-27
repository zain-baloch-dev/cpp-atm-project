```cpp
#include <iostream>
using namespace std;

int main()
{
    float balance = 100000, amount;
    int choice;
    char again;

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
                cout << " withdrawn balance is: " << amount << "pkr" << endl;
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
            cout << " cash deposit successfully " << endl;
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

        cout << " ***Thank you for using this ATM*** " << endl;

    } while (again == 'y' || again == 'Y');

    return 0;
}

```
