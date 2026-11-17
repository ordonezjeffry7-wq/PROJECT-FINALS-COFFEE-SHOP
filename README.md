#include <iostream>
using namespace std;

int main() {
    int serviceChoice, coffeeChoice, quantity, addMore;
    int americanoQty = 0, cappuccinoQty = 0;
    int latteQty = 0, mochaQty = 0;
    int total = 0;
    int counterNumber;

    cout << "===== Welcome to brewd++ =====\n";
    cout << "1. Dine-in\n";
    cout << "2. Take-out\n";
    cout << "Choose your order type: ";
    cin >> serviceChoice;

    if (serviceChoice != 1 && serviceChoice != 2) {
        cout << "Invalid choice.\n";
        return 0;
    }

    while (true) {
        cout << "\n===== COFFEE MENU =====\n";
        cout << "1. Americano - PHP 80\n";
        cout << "2. Cappuccino - PHP 110\n";
        cout << "3. Cafe Latte - PHP 120\n";
        cout << "4. Mocha - PHP 130\n";
        cout << "Choose a coffee: ";
        cin >> coffeeChoice;

        cout << "Enter quantity: ";
        cin >> quantity;

        if (quantity <= 0) {
            cout << "Invalid quantity.\n";
        }
        else if (coffeeChoice == 1) {
            americanoQty = americanoQty + quantity;
            total = total + (80 * quantity);
        }
        else if (coffeeChoice == 2) {
            cappuccinoQty = cappuccinoQty + quantity;
            total = total + (110 * quantity);
        }
        else if (coffeeChoice == 3) {
            latteQty = latteQty + quantity;
            total = total + (120 * quantity);
        }
        else if (coffeeChoice == 4) {
            mochaQty = mochaQty + quantity;
            total = total + (130 * quantity);
        }
        else {
            cout << "Invalid coffee choice.\n";
        }

        if (total > 0) {
            cout << "\n1. Add another coffee\n";
            cout << "2. Proceed to counter\n";
            cout << "Choose an option: ";
            cin >> addMore;

            if (addMore == 2) {
                break;
            }
        }
    }

    if (total == 0) {
        cout << "No items were ordered. Thank you for visiting brewd++!\n";
        return 0;
    }

    counterNumber = 100 + americanoQty
        + (cappuccinoQty * 2)
        + (latteQty * 3)
        + (mochaQty * 4);

    cout << "\n===== brewd++ RECEIPT =====\n";

    if (serviceChoice == 1) {
        cout << "Order type: Dine-in\n";
    }
    else {
        cout << "Order type: Take-out\n";
    }

    if (americanoQty > 0) {
        cout << "Americano x " << americanoQty
            << " - PHP " << americanoQty * 80 << "\n";
    }

    if (cappuccinoQty > 0) {
        cout << "Cappuccino x " << cappuccinoQty
            << " - PHP " << cappuccinoQty * 110 << "\n";
    }

    if (latteQty > 0) {
        cout << "Cafe Latte x " << latteQty
            << " - PHP " << latteQty * 120 << "\n";
    }

    if (mochaQty > 0) {
        cout << "Mocha x " << mochaQty
            << " - PHP " << mochaQty * 130 << "\n";
    }

    cout << "Total amount: PHP " << total << "\n";
    cout << "Counter number: " << counterNumber << "\n";
    cout << "Thank you for ordering at brewd++!\n";

    return 0;
}
