# Python_DSML
# Banking System

**Overview**
This Python program simulates a basic banking system. It allows users to:

Create a bank account.
Log in using account credentials.
Perform banking operations such as depositing money, withdrawing money, checking the account balance, and viewing the transaction history.
Logout or exit the system.

**Program Flow**
Start:
The program begins by showing the main menu with options to create an account, log in, or exit.

Account Creation:

Input: User provides name, account number, and PIN.
Output: Account is created and stored in the system.
Login:

Input: User provides account number and PIN.
Output: Access to the account menu if credentials are correct.
Account Menu Operations:

Deposit: Add a specified amount to the balance.
Withdraw: Deduct a specified amount from the balance, provided there are sufficient funds.
Check Balance: Display the current account balance.
View Transaction History: List all past transactions with timestamps.
Logout: Exit the account menu and return to the main menu.
Exit:
Gracefully terminates the program.


**Code Breakdown**
1. BankAccount Class
Purpose: Represents a user's bank account, managing account details, balance, and transaction history.

Attributes:

account_number: Unique identifier for the account.
name: Name of the account holder.
pin: A 4-digit PIN for authentication.
balance: Current balance in the account.
transactions: A list of tuples recording transactions (date, description).
Methods:

deposit(self, amount):
Adds money to the account. Appends the deposit details to the transaction history.
Parameters:
amount (float): Amount to deposit.
Output:
Confirms the deposit and displays the updated balance.

withdraw(self, amount):
Deducts money from the account if the balance is sufficient. Records the withdrawal in the transaction history.
Parameters:
amount (float): Amount to withdraw.
Output:
Confirms withdrawal or notifies if funds are insufficient.

check_balance(self):
Displays the current balance.

view_transaction_history(self):
Prints the history of all transactions, including the date and type.

2. BankingSystem Class
Purpose: Manages multiple user accounts and provides a menu-driven interface for interaction.

Attributes:

accounts: Dictionary to store all accounts (account_number as the key, BankAccount object as the value).
Methods:

create_account(self):
Guides the user to create a new account by providing their name, account number, and PIN.
Validations:

Ensures account number is unique.
Ensures the PIN is a 4-digit numeric value.
login(self):
Authenticates a user by checking the account number and PIN.
Output:
Returns the BankAccount object if login is successful or None otherwise.

run(self):
Main menu loop that offers the following choices:

Create a new account.
Login to an existing account.
Exit the program.
account_menu(self, account):
Provides an account-specific menu after login, with options to:

Deposit money.
Withdraw money.
Check balance.
View transaction history.
Logout.
