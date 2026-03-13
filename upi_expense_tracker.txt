expenses = []

while True:
    print("\n1 Add UPI Expense")
    print("2 View Expenses")
    print("3 Total Spending")
    print("4 Category Spending")
    print("5 Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        app = input("Payment App (PhonePe/GooglePay/Paytm): ")
        category = input("Category (Food/Travel/Shopping): ")
        amount = float(input("Amount: "))

        expenses.append((app, category, amount))
        print("Expense recorded!")

    elif choice == "2":
        print("\nAll Expenses:")
        for e in expenses:
            print("App:", e[0], "| Category:", e[1], "| Amount:", e[2])

    elif choice == "3":
        total = sum(e[2] for e in expenses)
        print("Total spent:", total)

    elif choice == "4":
        categories = {}

        for e in expenses:
            cat = e[1]
            amt = e[2]

            if cat in categories:
                categories[cat] += amt
            else:
                categories[cat] = amt

        print("\nSpending by Category:")
        for c in categories:
            print(c, ":", categories[c])

    elif choice == "5":
        print("Exiting program...")
        break

    else:
        print("Invalid choice")