

#include <iostream>
#include <string>

void exploreRoom(int roomNumber) {
    // Create a switch statement to represent different rooms in the adventure
    switch (roomNumber) {
        case 1:
            std::cout << "You are in a dark room. You see a door to the north." << std::endl;
            break;
        case 2:
            std::cout << "You enter a room with a table and a chest. The chest is locked." << std::endl;
            break;
        case 3:
            std::cout << "You find a key on the table. There's also a trapdoor on the floor." << std::endl;
            break;
        // Add more cases to represent different rooms and their descriptions
        default:
            std::cout << "You're in an unknown place." << std::endl;
            break;
    }
}

int main() {
    int currentRoom = 1;

    std::cout << "Welcome to the Text-Based Adventure Game!" << std::endl;
    std::cout << "Type 'quit' to exit the game." << std::endl;

    std::string userInput;
    while (true) {
        exploreRoom(currentRoom);

        if (currentRoom == 3) {
            std::cout << "You found the key! You won!" << std::endl;
            break;
        }

        std::cout << "Where do you want to go? (Type 'north', 'south', 'east', 'west'): ";
        std::cin >> userInput;

        if (userInput == "quit") {
            std::cout << "Exiting the game. Goodbye!" << std::endl;
            break;
        } else if (userInput == "north") {
            // Move to the next room if valid
            // For simplicity, the movement logic is not implemented
            currentRoom++;
        } else if (userInput == "south" || userInput == "east" || userInput == "west") {
            // Implement logic for other directions if needed
            std::cout << "You cannot go that way." << std::endl;
        } else {
            std::cout << "Invalid input. Try again." << std::endl;
        }
    }

    return 0;
}


