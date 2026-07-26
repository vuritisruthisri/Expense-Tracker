expenses = []

def add_expense():
    name = input("Enter Expense Name: ")
    amount = float(input("Enter Amount: "))
    expenses.append({"name": name, "amount": amount})
    print("Expense Added Successfully!")

def view_expenses():
    if len(expenses) == 0:
        print("No expenses found.")
    else:
        print("\nExpense List")
        for i, expense in enumerate(expenses, start=1):
            print(f"{i}. {expense['name']} - ₹{expense['amount']}")

def total_expense():
    total = sum(expense["amount"] for expense in expenses)
    print(f"\nTotal Spending: ₹{total}")

while True:
    print("\n===== Expense Tracker =====")
    print("1. Add Expense")
    print("2. View Expenses")
    print("3. Total Spending")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_expense()
    elif choice == "2":
        view_expenses()
    elif choice == "3":
        total_expense()
    elif choice == "4":
        print("Thank you for using Expense Tracker!")
        break
    else:
        print("Invalid Choice!")