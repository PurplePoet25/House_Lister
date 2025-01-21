# Program: Assignment-6 (bring up in IDLE)
#
# Programmer: Hasan Bukhari
#
# Date: 11/13/2024
#
# Description: The program displays a menu of options, allowing the user to select an action by entering a number between 1 and 6. It ensures 
#              that the input number is valid and, based on the selection, either lists all house records, displays the total inventory, prompts 
#              the user to add a new house, deletes a house by ID, finds a house by its ID, or edits the information of an existing house. 
#              If the user selects "Add a House," the program asks for the house’s unique ID, address, cost, square footage, and year built. 
#              Each new house is stored as a list within a list that holds all records. The program also reads existing house data from a 
#              file/database called `house.txt` and processes it accordingly. If the user chooses "Delete," "Find," or "Edit," the program 
#              searches for a matching house ID and either removes, displays, or edits the corresponding house details. After any changes, 
#              the program writes the updated data into a new file/database called `newhouse.txt`. This process repeats until the user selects "6" 
#              to exit, terminating the program.
#
# Requirements: Python 3.9 or greater
#
# Variable Library:
#   houses          - stores list of lists; each inner list contains details for a single house [ID, address, cost, square footage, year built]
#   house           - stores individual house details as a list, used when iterating over houses or adding a new house [ID, address, cost, square footage, year built]
#   house_id        - stores unique identifier for each house inputted by user
#   address         - stores address of the house inputted by user
#   cost            - stores cost of the house in dollars inputted by user
#   square_footage  - stores square footage of the house inputted by user
#   year_built      - stores the year the house was built inputted by user
#   num             - stores menu option selected by user to navigate program (1-5)
#   confirm         - stores user confirmation (yes/no) when deleting a house
#   data            - stores a line from the file that is read
#   database        - stores all of the content of the file that is read/written to
#   found           - stores True or False if house is found in the findhouse() function
#   total           - stores the total inventory in the showtotal() function
#   item            - stores every seperated element/item in the list (from the file) as it is converted into a string
#   option          - stores 1 for House ID# or 2 for Cost as the option in the findhouse() function

# Initializing variables
option = total = num = 0
item = database = data = confirm = house_id = address = cost = square_footage = year_built= " "
house = houses = []
found = False

# Opens a file called house.txt to access database
database = open("C:\\Users\\hasan\\Desktop\\house.txt","r")
# Reads a line from the file into variable called data
data = database.readline()

# Reads data until it runs out of it and stores each row/list in house which it appends into the 2D list (houses)
while data:

    # Converts row/list into a list and removes any leading/lagging whitespace characters
    house = data.strip().split("\t")

    # Ensure that all elements of the list are strings
    house = [str(item) for item in house]

    # Appends row/list into 2D list(houses) and then reads another line from the database/file
    houses.append(house)
    data = database.readline()

# listrecord() function prints out all records (that are available)
def listrecords(houses):

    # Checks for empty list, in which case prints that no house records are available
    if houses == []:
        print("No house records available.\n")

    else:
        # Formatting
        print(f"{'House ID#':^10} {'Address':^75} {'Cost($)':^25} {'Square Footage':^25} {'Year Built':^25}")
        print("- " * 80)

        # Stores each row/list in house and prints every row/list
        for house in houses:
            print(f"{house[0]:^10} {house[1]:^75} {house[2]:^25} {house[3]:^25} {house[4]:^25}")
        print(" \n")


# addhouse() function adds a house and its details to the 2D list (houses)
def addhouse(houses):

    # Inputs House ID#
    house_id = input("Enter House ID#: ")

    # Stores each row/list in house and iterates to check if first index is similar. If yes, prints out error message to make sure ID# is unique
    for house in houses:
         if house[0] == house_id:
            print("\nhouse ID# must be unique.\n")
            return # Exits function before data input so menu is printed again
         
    # Inputs address, cost, square footage, and year built associated with the House ID#
    address = input("Enter address: ")
    cost = input("Enter cost($): ")
    square_footage = input("Enter square footage: ")
    year_built = input("Enter year built: ")

    # Adds list/row to 2D list (houses)
    houses.append([house_id, address, cost, square_footage, year_built])
    print("\nHouse added successfully!\n") 


# deletehouse() function searches through 2D list (houses) and deletes desired list using House ID# after confirmation
def deletehouse(houses):

    # Inputs House ID#
    house_id = input("Enter House ID# to delete: ")
    print("")

    # Stores each row/list in house and iterates to check if it can find the desired House ID#
    for house in houses:
        if house[0] == house_id:

            # Prints out house information (if found) and asks for confirmation to delete it
            print(f"{'House ID#':^10} {'Address':^75} {'Cost($)':^25} {'Square Footage':^25} {'Year Built':^25}")
            print("- " * 80)
            print(f"{house[0]:^10} {house[1]:^75} {house[2]:^25} {house[3]:^25} {house[4]:^25}")
            print(" \n")
            confirm = input("Are you sure you want to delete this house? (y/n): ")
            if confirm.lower() == 'y':

                # Deletes list/row from 2D list (houses)
                houses.remove(house)
                print("\nHouse deleted successfully.\n")
                return # Exits function
            
    # Prints error message if House ID# not found
    print("\nHouse ID# not found.\n")


# findhouse() function searches through 2D list (houses) and prints out the desired list/row
def findhouse(houses):

    #Sets found as a global variable
    global found

    # Asks user's option for finding houses by either House ID# or Cost
    option = input("Search by 1-house ID# or 2-cost? (Enter 1/2): ")

    # Checks if option is House ID# (1) or Cost (2), otherwise prints an error message
    if option == "1":

        # Inputs House ID#
        house_id = input("Enter house ID# to find: ")
        print("")

        # Stores each row/list in house and iterates to check if it can find the desired House ID#
        for house in houses:
            if house[0] == house_id:

                # Updates found to True
                found = True

                # Prints out house information (if found) - basically the whole row/list
                print(f"{'House ID#':^10} {'Address':^75} {'Cost($)':^25} {'Square Footage':^25} {'Year Built':^25}")
                print("- " * 80)
                print(f"{house[0]:^10} {house[1]:^75} {house[2]:^25} {house[3]:^25} {house[4]:^25}")
                print(" \n")
                return # Exits function

    elif option == "2":

        # Inputs House ID#
        cost = input("Enter cost to find: ")
        print("")

        # Stores each row/list in house and iterates to check if it can find the desired House ID#
        for house in houses:
            if house[2] == cost:

                # Updates found to True
                found = True

                # Prints out house information (if found) - basically the whole row/list
                print(f"{'House ID#':^10} {'Address':^75} {'Cost($)':^25} {'Square Footage':^25} {'Year Built':^25}")
                print("- " * 80)
                print(f"{house[0]:^10} {house[1]:^75} {house[2]:^25} {house[3]:^25} {house[4]:^25}")
                print(" \n")
    else:
        # Prints error message when wrong option is inputted
        print("\nInvalid choice. Please select 1 or 2\n")
        return
    
    # Checks if house was found or not
    if not found:
        # Prints error message if house was not found
        print("\nHouse ID# not found.\n")


# edithouse() function to allow editing of house details
def edithouse(houses):

    # Inputs House ID#
    house_id = input("Enter House ID# to edit: ")
    print("")

    # Stores each row/list in house and iterates to check if it can find the desired House ID#
    for house in houses:
        if house[0] == house_id:

            # Prints current house details
            print(f"Current details for House ID# {house_id}:")
            print(f"{'House ID#':^10} {'Address':^75} {'Cost($)':^25} {'Square Footage':^25} {'Year Built':^25}")
            print("- " * 80)
            print(f"{house[0]:^10} {house[1]:^75} {house[2]:^25} {house[3]:^25} {house[4]:^25}")
            print("")

            # Ask user for new details and update the house list
            house[1] = input(f"Enter new address (current: {house[1]}): ")
            house[2] = input(f"Enter new cost (current: {house[2]}): ")
            house[3] = input(f"Enter new square footage (current: {house[3]}): ")
            house[4] = input(f"Enter new year built (current: {house[4]}): ")

            print("\nHouse details updated successfully!\n")
            return

    # Prints error message if House ID# not found
    print("\nHouse ID# not found.\n")


# showtotal() function adds up all costs and displays the total value as total inventory
def showtotal(houses):

    global total
    total = 0  # Initialize the total value of all houses

    # Iterate through the list of houses and sum up the costs
    for house in houses:
        total += int(house[2])  # Convert the cost to an integer and add it to total

    # Print out the total value
    print(f"\nTotal Inventory Value: ${total}\n")


# Printing out database with function call before menu
print("")
listrecords(houses)

# Loop to request number between 1 and 4 from user which only breaks when number is between 1 and 5 inclusively
while num < 1 or num > 7:

    # Printing out menu
    print ("Choices for Menu \n\t1) List Records \n\t2) Add a House \n\t3) Delete a House \n\t4) Find a House \n\t5) Edit a House \n\t6) Show Total Inventory \n\t7) Exit ")

    # Requesting a number from user and storing it in variable 'num'
    num = int(input("\tPlease enter a number (1-7): "))
    print("")

    # Checks if number is between 1 and 5 inclusively, otherwise prints an error message and restarts loop 
    if num >= 8 or num <= 0:
        print("Invalid choice. Please select a number between 1 and 7 \n")
        continue

    # Calls function respective to chosen option (for input), or jumps out of loop and prints name, age, and height when 4/Exit is chosen
    match num:
        case 1:
            listrecords(houses)
            num = 0
        case 2:
            addhouse(houses)
            num = 0
        case 3:
            deletehouse(houses)
            num = 0
        case 4:
            findhouse(houses)
            num = 0
        case 5:
            edithouse(houses)
            num = 0
        case 6:
            showtotal(houses)
            num = 0
        case 7:
            # Open the file and write the houses data to newhouse.txt
            database = open("C:\\Users\\hasan\\Desktop\\newhouse.txt", "w")
            for house in houses:
                database.write("\t".join(house) + "\n")
            database.close()
            
            print("\nExiting program and saving data to newhouse.txt.")
            break  # Exit the loop and end the program
