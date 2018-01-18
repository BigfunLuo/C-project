# Cplus-plus-project
#include<iostream>
#include<string>
using namespace std;
void displaytitle(string title)  //function of display the title
{
	cout << "\t";
	for (int i = 0; i < title.length(); i++) //using the for loop of displaying the underline 
	{
		cout << char(toupper(title[i]));  //toupper is an array of char function to let the letter became upper case. 
	}
	cout << "\n\t";
	for (int i = 1; i <= title.length(); i++)
	{
		cout << "-";
	}
	cout << "\n\n";
}
void readname(string name)  //function of read the name
{
	
	cout << "\tby: "<< name;
	cout << "\n\t";
	for (int i = 1; i <= name.length(); i++)
	{
		cout << "-";
	}
	cout << "\n\n";

}
void displaylist() //function of displaying the menu list
{
	cout << "1 - Addition \n";
	cout << "2 - Division \n";
	cout << "3 - Substiaction \n";
	cout << "4 - Multiplication \n";
	cout << "5 - Exit \n";
}
int chooseoperation() //function of require the choice.
{   
	int  NBoperation;
	do {                                             //using do-while loop to display text first and store the value.
		cout << "Enter your choice(1-5): ";
		cin >> NBoperation;
	} while (NBoperation < 1 || NBoperation>5);
   return NBoperation;
   
}	
void addition()   //function of addition 
{
	int nb;
	float value, sum = 0;
	cout << "\tCALCULATOR\n";
	cout << "\t_______________\t\n";
	cout << "\tADDITION\n";
	cout << "\t_______________\t\n";
	cout << "Enter the number of value to add:";
	cin >> nb;
	for (int i = 0; i < nb; i++)
	{
		cout << "Enter value" << i + 1 << " : ";
		cin >> value;
		sum += value;
	}
	cout << "The result of the addition is " << sum << endl;
}
void division()   //function of division
{
	
	float divide, dividor,sum;
		cout << "\tCALCULATOR\n";
		cout << "\t_______________\t\n";
		cout << "\tDIVISION\n";
		cout << "\t_______________\t\n";
		cout << "Enter the value to divide:";
		cin >> divide;
		cout << "Enter the dividor: ";
		cin >> dividor;
		sum = divide / dividor;
		cout << "The result of the division is " << sum << endl;
	
}
void substiaction()   //function of substiaction
{
	float substiacte ,substiactor, sum;
		cout << "\tCALCULATOR\n";
		cout << "\t_______________\t\n";
		cout << "\tSUBSTIACTION\n";
		cout << "\t_______________\t\n";
		cout << "Enter the value to substiacte:";
		cin >> substiacte;
		cout << "Enter the substiactor: ";
		cin >> substiactor;
		sum = substiacte - substiactor;
		cout << "The result of the substiaction is " << sum << endl;
	
}
void multiplication()   //function of multiplication
{
	int nb,sum = 1;   //the  multiplication is different from the other operations because the variable of sum should be declared the value 1. 
	float value;
	cout << "\tCALCULATOR\n";
	cout << "\t_______________\t\n";
	cout << "\tMULTIPLICATION\n";
	cout << "\t_______________\t\n";
	cout << "Enter the number of value to mulitplie:";
	cin >> nb;
	for (int i = 0; i < nb; i++)
	{
		cout << "Enter value" << i + 1 << " : ";
		cin >> value;
		sum =sum* value;
	}
	cout << "The result of the mulitplication is " << sum << endl;
}
void switchoperation(int operation) //funuction of choosing the operations
{
	
	if (operation == 1)       //the switch case also can be used. 
  {        
		addition();
	}
	else if (operation == 2) 
  {
		division();
	}
	else if (operation == 3) 
  {
		substiaction();
	}
	else if (operation == 4) 
  {
		multiplication();
	}
	else if (operation == 5)
  {
		cout << "you have exited the program!";
		exit(0);
	}
}
char repeatoperation()  //function of repe
{
	char choice;
	do {
		cout << "Do you want to do another operation(Y/N) :";
		cin >> choice;
	} while (toupper(choice) != 'Y'&& toupper(choice) != 'N');
	return toupper(choice);
}
void ClearScreen()
{
	/*cout << string(100, '\n');*/
	system("CLS");
}
int main()
{
	int operation;
	char run;
	displaytitle("CALCULATOR");
	readname("Xiufen Luo");
	while (true) {
		displaylist();
		operation = chooseoperation();
		ClearScreen();
		while (true)
		{
			switchoperation(operation);
			run = repeatoperation();
			ClearScreen();
			if (run == 'N')
			{
				displaytitle("CALCULATOR");
				readname("Xiufen Luo");
				break;
			}

		}
	}
}
