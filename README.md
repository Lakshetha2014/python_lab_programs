# python_lab_programs
# python lab -1 
# Function to add two numbers
def add_numbers(a, b):
    return a + b

# Taking input from user
num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))

# Calling the function
result = add_numbers(num1, num2)

print("The sum is:", result)

# Program to check if a number is positive, negative, or zero
# Input from user
num = float(input("Enter a number: "))

if num > 0:
    print("The number is Positive")
elif num < 0:
    print("The number is Negative")
else:
    print("The number is Zero")

# Example: Count vowels in a string

def count_vowels(text):
    vowels = "aeiouAEIOU"
    count = 0
    for char in text:
        if char in vowels:
            count += 1
    return count

sentence = input("Enter a sentence: ")
print("Number of vowels:", count_vowels(sentence))


#python lab - 6
 # Example: 1.Method overloading using default arguments
 
 
class Vehicle:
    def description(self, wheels=None, color=None): # Method overloading using default arguments
        if wheels is not None and color is not None:
            print(f"This vehicle has {wheels} wheels and is {color} in color.")
        elif wheels is not None:
            print(f"This vehicle has {wheels} wheels.")
        else:
            print("This is a vehicle.")


class Bus(Vehicle):      
    def description(self, wheels=None, capacity=None):# Method overloading using default arguments
        if wheels is not None and capacity is not None:
            print(f"This bus has {wheels} wheels and a capacity of {capacity} passengers.")
        elif wheels is not None:
            print(f"This bus has {wheels} wheels.")
        else:
            print("This is a bus.")

v = Vehicle()
v.description()                 # Overloaded method 1
v.description(2)                # Overloaded method 2
v.description(4, "Red")         # Overloaded method 3

print()

b = Bus()
b.description()                  # Overloaded method 1
b.description(6)                 # Overloaded method 2
b.description(6, 50)             # Overloaded method 3

# Example 2:  Using *args for Method Overloading in Vehicle class

class Vehicle:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    # Method overloading using *args
    def vehicle_info(self, *args):
        info = f"Vehicle: {self.brand} {self.model}"
        if len(args) == 1:
            info += f", Year: {args[0]}"
        elif len(args) == 2:
            info += f", Year: {args[0]}, Color: {args[1]}"
        print(info)


v = Vehicle("Toyota", "Corolla")
v.vehicle_info()             # No extra args
v.vehicle_info(2023)         # One extra arg
v.vehicle_info(2025, "Red")  # Two extra args

