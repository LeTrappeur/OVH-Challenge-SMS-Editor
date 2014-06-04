// Read inputs from stdin. Write outputs to stdout.

#include <iostream>
#include <string>
#include <map>
#include <vector>

// Cst
const int SMS_MAX_SIZE = 160;
const char SMS_INPUT_SPACE = ' ';

// Phone keys
const std::map<char, std::vector<char>> inputsToCharMap
{
    {'0', {' ', '0'}},
    {'1', {'1'}},
    {'2', {'a', 'b', 'c', '2'}},
    {'3', {'d', 'e', 'f', '3'}},
    {'4', {'g', 'h', 'i', '4'}},
    {'5', {'j', 'k', 'l', '5'}},
    {'6', {'m', 'n', 'o', '6'}},
    {'7', {'p', 'q', 'r', 's', '7'}},
    {'8', {'t', 'u', 'v', '8'}},
    {'9', {'w', 'x', 'y', 'z', '9'}}
};

// Get message string from user inputs
std::string getStringFromInputs(const std::string& inputs)
{
    std::string message;
    int counter(0);
    char currentLetter(inputs[0]);
    int index(0);

    while(index <= inputs.length())
    {
        // Key is repeated ?
        if(currentLetter == inputs[index+1])
        {
            counter++;
        }
        else
        {
            if(currentLetter != SMS_INPUT_SPACE && message.length() < SMS_MAX_SIZE)
            {
                // User is able to loop characters
                counter = counter % inputsToCharMap.at(currentLetter).size();
                // Look up at the key table to add the right character
                message.push_back(inputsToCharMap.at(currentLetter).at(counter));
            }
            counter = 0;
        }
        index++;
        currentLetter = inputs[index];
    }
    return message;
}

int main()
{
	std::string inputs;
	// Second line read, size can be ignored
	getline(std::cin, inputs);
	getline(std::cin, inputs);

	std::string msg = getStringFromInputs(inputs);

	std::cout << msg << std::endl;

	return 0;
}
