# Code is written for the Assignment 5 "THE PROJECT"

# Code is Written by Talha Bin Tariq, Vishan Dilanka Costa Warnakulasuriya,
#   Lakshani Rageetha Punchi Banda, Yunchao Jiang, Thi Hong Thanh Nguyen.




import math                                                      # Importing math library for the calculations

# Function for addition

def addition(x, y):
    return x + y



# Function for subtraction

def subtraction(x, y):
    return x - y



# Function for multiplication

def multiplication(x, y):
    return x * y



# Function for division

def division(x, y):
    if y == 0:
        return "Error! Division by zero!"
    return x / y



# Function for raising a number to the second power

def second_power(x):
    return x ** 2



# Function for calculating square root

def square_root(x):
    if x < 0:
        return "Error! Square root of a negative number!"
    return math.sqrt(x)



# Function to display the menu options

def display_menu():
    print("\nCalculator Functions Menu:")
    print("1. Addition")
    print("2. Subtraction")
    print("3. Multiplication")
    print("4. Division")
    print("5. Second Power")
    print("6. Square Root")
    print("7. Exit")

    
    
# Function to get the user's choice of operation

def get_operation_choice():
    while True:
        choice = input("Enter your choice (1-7): ")
        if choice.isdigit() and 1 <= int(choice) <= 7:
            return int(choice)
        else:
            print("Invalid choice! Please enter a number between 1 and 7.")

            
# Function to get input numbers from the user

def get_numbers():
    while True:
        try:
            x = float(input("Enter the first number: "))
            y = float(input("Enter the second number: "))
            return x, y
        except ValueError:
            print("Invalid input! Please enter numeric values.")

            
            
# Main function to run the calculator

def main():
    while True:
        display_menu()                                        # Display the calculator menu
        choice = get_operation_choice()                       # Get the user's choice of operation
        
        # Exit if choice is 7
        
        if choice == 7:
            print("Exiting the calculator. Goodbye!")
            break
        
        
        # Perform arithmetic operations if choice is 1-4 (+ - x /)
        
        if choice in [1, 2, 3, 4]:
            x, y = get_numbers()                              # Get input numbers
            
            if choice == 1:
                print("Result:", addition(x, y))
            elif choice == 2:
                print("Result:", subtraction(x, y))
            elif choice == 3:
                print("Result:", multiplication(x, y))
            elif choice == 4:
                print("Result:", division(x, y))
                
                
        # Perform other operations if choice is 5 or 6 (power & squreroot)
        
        elif choice in [5, 6]:
            
            x = float(input("Enter the number: "))
            
            if choice == 5:
                print("Result:", second_power(x))
            elif choice == 6:
                print("Result:", square_root(x))
                
        # To Handle invalid choices    
        
        else:
            print("Invalid choice! Please enter a number between 1 and 7.")

            
# Executing the main function

if __name__ == "__main__":
    main()

