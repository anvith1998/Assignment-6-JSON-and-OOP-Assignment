# Assignment-6-JSON-and-OOP-Assignment

Q- GitHub Link -> https://github.com/edyoda/DS-Assignments/blob/main/JSON_and_OOPS_Assignment.md

#Assignment 1
#👉 1. Create a JSON file (employee.json) containing employee information of minimum 5 employees. Each employee information consists of Name, DOB, Height, City, State. Write a python program that reads this information from the JSON file and saves the information into a list of objects of Employee class. Finally print the list of the Employee objects.

employee.json

[
  {
    "Name": "John Doe",
    "DOB": "10/02/1980",
    "Height": "5'10",
    "City": "New York",
    "State": "New York"
  },
  {
    "Name": "Jane Doe",
    "DOB": "09/04/1985",
    "Height": "5'7",
    "City": "San Francisco",
    "State": "California"
  },
  {
    "Name": "John Smith",
    "DOB": "01/10/1993",
    "Height": "6'2",
    "City": "Chicago",
    "State": "Illinois"
  },
  {
    "Name": "Jane Smith",
    "DOB": "03/09/1989",
    "Height": "5'5",
    "City": "Los Angeles",
    "State": "California"
  },
  {
    "Name": "Henry Johnson",
    "DOB": "07/07/1978",
    "Height": "6'0",
    "City": "Boston",
    "State": "Massachusetts"
  }
]

import json

class Employee:
    def __init__(self, name, dob, height, city, state):
        self.name = name
        self.dob = dob
        self.height = height
        self.city = city
        self.state = state

employees = []

with open('employee.json') as json_file:
    data = json.load(json_file)
    for employee in data:
        employees.append(Employee(employee['Name'], employee['DOB'], employee['Height'], employee['City'], employee['State']))

for employee in employees:
    print(employee.name, employee.dob, employee.height, employee.city, employee.state)
    
===============================================================
   
#Create a dictionary of any 7 Indian states and their capitals. Write this into a JSON file.

{
"Maharashtra": "Mumbai",
"Uttar Pradesh": "Lucknow",
"Karnataka": "Bengaluru",
"Rajasthan": "Jaipur",
"Gujarat": "Gandhinagar",
"Goa": "Panaji",
"Kerala": "Thiruvananthapuram"
}

JSON File:

{
    "Maharashtra": "Mumbai",
    "Uttar Pradesh": "Lucknow",
    "Karnataka": "Bengaluru",
    "Rajasthan": "Jaipur",
    "Gujarat": "Gandhinagar",
    "Goa": "Panaji",
    "Kerala": "Thiruvananthapuram"
}


#Assignment 2
#Create a class named ‘Dog’. It should have a constructor which accepts its name, age and coat color. You must perform the following operations:

🔴 a. It should have a function ‘description()’ which prints the name and age of the dog.
🔴 b. It should have a function ‘get_info()’ which prints the coat color of the dog.
🔴 c. Create child classes ‘JackRussellTerrier’ and ‘Bulldog’ which is inherited from the class ‘Dog’. It should have at least two methods of its own.
🔴 d. Create objects and implement the above functionalities.

class Dog:
    def __init__(self, name, age, coat_color):
        self.name = name
        self.age = age
        self.coat_color = coat_color

    def description(self):
        print("The dog's name is " + self.name + " and it is " + str(self.age) + " years old.")

    def get_info(self):
        print("The coat color of the dog is " + self.coat_color + ".")


class JackRussellTerrier(Dog):
    def __init__(self, name, age, coat_color):
        super().__init__(name, age, coat_color)

    def bark(self):
        print("Woof Woof!")

    def jump(self):
        print("The Jack Russell Terrier is jumping!")


class Bulldog(Dog):
    def __init__(self, name, age, coat_color):
        super().__init__(name, age, coat_color)

    def bark(self):
        print("Grrrr!")

    def sit(self):
        print("The Bulldog is sitting!")


# Creating objects
dog1 = Dog("Max", 5, "brown")
dog2 = JackRussellTerrier("Lucy", 2, "white")
dog3 = Bulldog("Buddy", 3, "black")

# Implementing functionalities
dog1.description()
dog1.get_info()
dog2.description()
dog2.get_info()
dog2.bark()
dog2.jump()
dog3.description()
dog3.get_info()
dog3.bark()
dog3.sit()
