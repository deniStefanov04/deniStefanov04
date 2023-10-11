#include <iostream>
using namespace std;

const int max_opci_menu = 3;
const int N = 10; // Добавете точка и запетая (;) след константата N

int menu(); // Декларация на функцията menu()
void inputArray(int arr[], const unsigned int size);
void printArray(const int arr[], const unsigned int size);

int main()
{
    int menuOpcia = 0;
    int arr[N];

    do
    {
        menuOpcia = menu(); // Извикване на функцията menu()

        system("CLS"); // Изчистване на екрана след избор на опция

        switch (menuOpcia)
        {
            case 1: inputArray(arr, N); break;
            case 2: printArray(arr, N); break;
            case 3: cout << "Край на програмата" << endl; break; // Коригиране на правописната грешка
        }

        system("pause");
        system("CLS"); // Изчистване на текста след приключване на изпълнението на опцията
    } while (menuOpcia < max_opci_menu);

    return 0;
}

int menu()
{
    int choice = 0; // Коригиране на правописната грешка, "choise" вместо "choice"

    cout << "*** Меню ***" << endl;
    cout << "1. Въвеждане на стойностите на масива" << endl;
    cout << "2. Извеждане на масива" << endl;
    cout << "3. Изход" << endl;

    // Въвеждане на избора от менюто
    do
    {
        cout << "Изберете опция: ";
        cin >> choice;
    } while (choice < 1 || choice > max_opci_menu);

    return choice;
}

void inputArray(int arr[], const unsigned int size)
{
    for (int i = 0; i < size; i++)
    {
        cout << "arr[" << i << "] = ";
        cin >> arr[i];
    }
}

void printArray(const int arr[], const unsigned int size)
{
    for (int i = 0; i < size; i++)
    {
        cout << arr[i] << endl;
    }
}

