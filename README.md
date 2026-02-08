' expense tracker app'
def menu():
    print('=== cash expense tracker ===')
    print('1. add expense')
    print('2. view expenses by category')
    print('3. total expenses')
    print('4. exit')
expenses = []
while True:
    menu()
    choice = input('choose(1-4):')
    print(f'you chose {choice}')
    if choice == '1':
        amount = float(input('enter expense amount:'))
        category = input('enter expense category:')
        expenses.append({'amount': amount, 'category': category})
        print('expense added successfully!')
    elif choice == '2':
        if len (expenses) == 0:
            print('no expenses recorded yet.')
        else:
            for expense in expenses:
                print(f"Amount: {expense['amount']}, Category: {expense['category']}")
    elif choice == '3':
        total = sum(expense['amount'] for expense in expenses)
        print(f'total expenses: {total}')
    elif choice == '4':
        print('exit')
        break
