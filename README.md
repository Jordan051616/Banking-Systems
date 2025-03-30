# Banking-Systems
#include <iostream>
#include <string>
#include <vector>

class Account {
public:
    std::string accountNumber;
    std::string accountHolderName;
    double balance;

    Account(std::string number, std::string name, double initialBalance) : accountNumber(number), accountHolderName(name), balance(initialBalance) {}

    void deposit(double amount) {
        balance += amount;
        std::cout << "Deposit successful. New balance: " << balance << std::endl;
    }

    void withdraw(double amount) {
        if (balance >= amount) {
            balance -= amount;
            std::cout << "Withdrawal successful. New balance: " << balance << std::endl;
        } else {
            std::cout << "Insufficient balance." << std::endl;
        }
    }

    void checkBalance() const {
        std::cout << "Account balance for " << accountHolderName << ": " << balance << std::endl;
    }
};

int main() {
    // Create an account
    Account myAccount("123456789", "John Doe", 1000.0);

    // Perform operations
    myAccount.checkBalance();
    myAccount.deposit(500.0);
    myAccount.withdraw(200.0);
    myAccount.withdraw(2000.0);
    myAccount.checkBalance();

    return 0;
}
