# codsoft_2
//Develop a program that counts the number of words in a given
text file. Prompt the user to enter the file name and display the
total word count.

#include <iostream>
#include <fstream>
#include <string>
#include <sstream>

using namespace std;

int main() {
    string fileName;
    cout << "Enter the name of the text file: ";
    cin >> fileName;

    ifstream inputFile(fileName);

    if (!inputFile) {
        cerr << "Error: Unable to open file." << endl;
        return 1; // Exit with an error code
    }

    string line;
    int wordCount = 0;

    while (getline(inputFile, line)) {
        stringstream ss(line);
        string word;

        while (ss >> word) {
            wordCount++;
        }
    }

    inputFile.close();

    cout << "Total word count in the file: " << wordCount << endl;

    return 0;
}
