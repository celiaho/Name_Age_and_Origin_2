// Description: This program 
//		customizes the title bar;
//		customizes the color of the cmp window;
//		prints a centered banner using the WYSIWYG approach;
//		prints a statement with user's city and calculated age;
//		holds the screen so the user will see the final message; and
//		illustrates use of
//			strings, 
//			constant variables, 
//			escape sequences, 
//			cin functions and methods, and 
//			removing extra data from the keyboard buffer so the next input starts fresh. 
//		Instruction files: https://bhcc.digication.com/cit120all_master_delta/ and 
//			Pr3-18.cpp https://online.bhcc.edu/pluginfile.php/2975258/mod_folder/content/0/Pr3-18%20.cpp?forcedownload=1
// Title: Name, Age and Origin
// Programmer: C. Ho
// Last Modified: Mon. Oct. 2, 2023 @ 4:15 PM

// PREPROCESSOR DIRECTIVE SECTION
#include <iostream>
#include <string>
using namespace std;

// FUNCTION DECLARATION SECTION, INCLUDING FUNCTION PROTOTYPES - N/A IN THIS LAB

// MAIN SUB-SECTION
int main()
{
	// SET UP SECTION
	// System function call to change text in title bar
	system("title Strings, Constant Variables, Escape Sequences, and cin Functions + Methods 2     by C. Ho");
	// System function call to change the color of the cmp window (background, foreground)
	system("color E1");

	// Centered banner using the WYSIWYG approach
	cout << "\n"
		<< "\t\t\t                   Full name, year of birth and city                 \n"
		<< "\t\t\t       Not as easy as it looks - the devil is in the details!        \n"
		<< "\t\t\t                Make sure you test EVERY possible input.             \n"
		<< "\t\t\t             Name and city can have 1, 2, 3, or more parts.          \n"
		<< "\t\t\t   After the year born there could be another input in that line.    \n"
		<< "\t\t\t                       Base year is set to 2023.                     \n"
		<< "\t\t\t Make sure you follow all the learning outcomes of the previous lab. \n"
		<< "\t\t\t                                Lab #2                               \n"
		<< "\t\t\t                               by C. Ho                              \n\n\n";

	// VARIABLE DECLARATION SECTION
	string name, city;
	int birthYear;
	const int CURRENT_YEAR = 2023;

	// INPUT SECTION
	// Get the user's name.
	cout << "Please enter your name: ";
	cin >> ws;													// Optional: Discard the input buffer and initial white spaces of string.
	getline(cin, name);											// Allows names with spaces and special characters

	// Get the user's birth year.
	cout << "What year were you born, \"" << name << "\"? ";
	cin >> birthYear;
	cin.ignore(1000, '\n');										// Allow birth year to be entered with subsequent inputs.
	while (birthYear < 0 || birthYear > CURRENT_YEAR)			// Optional: Validate birth year
	{
		cout << "ERROR: Enter a value in the range 0-" << CURRENT_YEAR <<": ";
		cin >> birthYear;
		cin.ignore(1000, '\n');									// Allow birth year with additional input following.
	}
	
	// Get the user's city.
	cout << "Enter the city you live in: ";
	cin >> ws;													// Optional: Discard the input buffer and initial white spaces of string.
	getline(cin, city);											// Allow names with spaces and special characters.

	// PROCESSING SECTION - N/A IN THIS LAB

	// OUTPUT SECTION
	// Print a statement with user's city and calculated age.
	cout << "\n   You are from \"" << city << "\" and as of " << CURRENT_YEAR << " you are " << CURRENT_YEAR - birthYear << " years old.\n\n";
	
	// CLEAN UP SECTION
	// Hold screen so user will see the final message.
	system("pause"); 
	return 0;
// MAIN ENDS
}