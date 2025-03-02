
# House Lister Program

## Programmer: Hasan Bukhari  
## Date: 11/13/2024  

### Description:
This Python program allows users to manage a list of houses through a menu-driven interface. The program provides the following options:

1. List all house records.
2. Add a new house with specified details such as ID, address, cost, square footage, and year built.
3. Delete a house by its ID after confirming the deletion.
4. Find a house by either House ID# or Cost.
5. Edit an existing house's details.
6. Show the total inventory value based on the cost of all houses.
7. Exit the program.

The program reads house data from a file called `houses.txt` (which should be specified with the correct file path) and writes any changes back to a new file called `newhouses.txt`.

### Requirements:
- Python 3.9 or greater
- A `houses.txt` file containing existing house data. Each house record is stored in a tab-separated format with the following details:
  - House ID#
  - Address
  - Cost ($)
  - Square Footage
  - Year Built

### File Structure:
1. `houses.txt` (text file containing house records to be loaded by the program).
2. `newhouses.txt` (output file where updated house data is saved after any modifications).

### Instructions:
1. Place the `houses.txt` file in the same directory as the program or specify its file path in the code.
2. Run the program in a Python 3.9+ environment.
3. Use the menu options to interact with the program and manage house records.

### Example usage:

- When adding a house, you will be prompted to enter a unique House ID#, address, cost, square footage, and year built.
- When deleting a house, you'll need to input the House ID# and confirm the deletion.
- Searching for a house can be done either by House ID# or Cost.
- Editing a house allows you to update the address, cost, square footage, and year built of an existing house.

### Contact Information:
For any issues or questions, feel free to reach out to the programmer, Hasan Bukhari.
