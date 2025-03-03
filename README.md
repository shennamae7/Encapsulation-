class BankAccount:
    def __init__(self, account_number, balance=0):
        self.__account_number = account_number  # Private attribute
        self.__balance = balance  # Private attribute

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"Deposited: ₱{amount}. New balance: ₱{self.__balance}")
        else:
            print("Deposit amount must be positive.")

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            print(f"Withdrew: ₱{amount}. New balance: ₱{self.__balance}")
        else:
            print("Invalid withdrawal amount.")

    def get_balance(self):
        return self.__balance

    def get_account_number(self):
        return self.__account_number


# Example usage
account = BankAccount("324680291")
account.deposit(500)
account.withdraw(300)
print(f"Account Number: {account.get_account_number()}")
print(f"Current Balance: ₱{account.get_balance()}")

# Trying to access private attributes directly will raise an error
# print(account.__balance)  # This will raise an AttributeError
