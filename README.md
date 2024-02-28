#User Input and Data Management: Develop a system that allows users to input their daily expenses.
#Data Storage: Implement a mechanism to store and manage the entered expense data.
#Expense Categories: Categorize expenses into different categories for better organization.
#Data Analysis: Provide users with insights into their spending patterns, such as monthly summaries and category-wise expenditure.
#User-Friendly Interface: Create a user-friendly interface for a seamless user experience.
#Error Handling: Implement error handling to ensure the application can handle unexpected inputs gracefully.
#Documentation: Document your code effectively to demonstrate clarity and understanding.
expenses = []
expense1 = {'amount': '51.00', 'category': 'transportation'}
expenses.append(expense1)

expense2 = {'amount': '21.55', 'category': 'food'}
expenses.append(expense2)

#remove the expense in list
def removeExpense():
  while True:
    listExpenses()
    print("What expense would you like to remove?")
    try:
      expenseToRemove = int(input("> "))
      del expenses[expenseToRemove]
      break
    except:
      print("Invalid input. Please try again.")

# add the expense in list
def addExpense(amount, category):
  expense = {'amount': amount, 'category': category}
  expenses.append(expense)

# choose the option in the expense
def printMenu():
  print("Please choose from one of the following options...")
  print("1. Add A New Expense")
  print("2. Remove An Exepense")
  print("3. List All Exepenses")


def listExpenses():
  print("\nHere is a list of your expenses...")
  print("------------------------------------")
  counter = 0
  for expense in expenses:
    print("#", counter, " - ", expense['amount'], " - ", expense['category'])
    counter += 1
  print("\n\n")


if _name_ == "_main_":
  while True:
    ### Prompt the user
    printMenu()
    optionSelected = input("> ")

    if (optionSelected == "1"):
      print("How much was this expense?")
      while True:
        try:
          amountToAdd = input("> ")
          break
        except:
          print("Invalid input. Please try again.")

      print("What category was this expense?")
      while True:
        try:
          category = input("> ")
          break
        except:
          print("Invalid input. Please try again.")

      addExpense(amountToAdd, category)
    elif (optionSelected == "2"):
      removeExpense()
    elif (optionSelected == "3"):
      listExpenses()
    else:
      print("Invalid input. Please try again.")
