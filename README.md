# Project: Family Management System

This project implements a family management system in C++ which stores and manages data about families and their participation in clubs. The data is stored in a binary file (`families.txt`) and can be modified using various operations such as adding, deleting, updating, and checking the participation of families in different clubs.

## Features

- **Add Family**: Add a new family with details such as family number, name, number of people, and phone number.
- **Delete Family**: Delete a family from the file by family number.
- **Update Family**: Update the club participation for a specific family. Families can join or leave clubs based on the availability.
- **Update Waiting Families**: Move families from the waiting list to a club if there is space.
- **Check Club Participation**: Check if a specific family is participating in a specific club.
- **Print Family Details**: Print the details of a family by family number.
- **Print Families in Club**: Print all families that are participating in a specific club.

## Functions

### 1. `setFile(std::fstream& file)`
Initializes the file by writing empty Family objects to the binary file.

### 2. `add(std::fstream& file)`
Prompts the user to enter a family number, name, number of people, and phone number, and adds the family to the file.

### 3. `del(std::fstream& file, int index)`
Deletes the family at the specified index in the file by writing an empty `Family` object at that position.

### 4. `update(std::fstream& file, int index, std::queue<Family>& waitingQueue)`
Allows updating the club participation of a family. If a family cannot join a club due to space limitations, it is added to the waiting queue.

### 5. `waiting(std::fstream& file, std::queue<Family>& waitingQueue)`
Moves families from the waiting queue into clubs if space is available.

### 6. `rishum(std::fstream& file, int index, int club)`
Checks if a family is registered for a specific club.

### 7. `print(std::fstream& file, int index)`
Prints the details of a specific family, including their name, number of people, phone number, and active clubs.

### 8. `inClass(std::fstream& file, int c)`
Prints all families participating in a specific club.
## How to Run

1. Compile the program:
   ```bash
   g++ -o family_manager family_manager.cpp
   ```

2. Run the program:
   ```bash
   ./family_manager
   ```

3. Follow the on-screen prompts to manage families and their club participation.

4. You will be prompted to choose an action such as:
   - Add a new family
   - Delete an existing family
   - Update family participation
   - View family details
   - View families in a specific club

5. The data will be stored in a binary file (`families.txt`) which will persist even after the program is closed. You can reopen the program to continue making changes or view the current data.

## File Structure

- `families.txt`: The binary file where family data is stored.
- `Family.h`: Contains the structure definition for the `Family` class.
- `family_manager.cpp`: The main C++ source code for the family management system.

## Error Handling

- Invalid family numbers (outside the range of 1-100) will throw an error.
- Attempting to add a family where one already exists will result in an error.
- Clubs with more than 10 families will reject new entries.
- Various other checks are in place to ensure data integrity, such as validating phone numbers and number of people in a family.

## Notes

- The file `families.txt` must be present in the same directory as the program for it to function correctly.
- The program assumes that all families will be indexed by their family number (1-100).
- You can manually modify the `families.txt` file, but ensure it maintains the correct binary format to avoid corruption.

## Future Improvements

- Implement a more advanced user interface (GUI) for easier interaction.
- Allow exporting the family data to a readable format like CSV or JSON.
- Add additional functionality to support more clubs and better handle club capacity.

