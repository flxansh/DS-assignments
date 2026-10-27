#include <iostream>
using namespace std;

// Linked List Node
struct Patient
{
    int id;
    string name;
    int age;
    string disease;
    Patient* next;
};

Patient* head = NULL;

// Hash Table
const int SIZE = 10;
Patient* hashTable[SIZE] = {NULL};

// Hash Function
int hashFunction(int id)
{
    return id % SIZE;
}

// Register New Patient
void registerPatient()
{
    Patient* p = new Patient;
    
    cout << "Enter Patient ID: ";
    cin >> p->id;
    
    cout << "Enter Name: ";
    cin >> p->name;
    
    cout << "Enter Age: ";
    cin >> p->age;
    
    cout << "Enter Disease: ";
    cin >> p->disease;
    
    p->next = head;
    head = p;

    // Insert into Hash Table using Chaining
    int index = hashFunction(p->id);
    p->next = hashTable[index];
    hashTable[index] = p;

    cout << "Patient registered successfully!\n";
}

// Search Patient
void searchPatient()
{
    int id;
    cout << "Enter Patient ID to search: ";
    cin >> id;

    int index = hashFunction(id);
    Patient* temp = hashTable[index];

    while (temp != NULL)
    {
        if (temp->id == id)
        {
            cout << "Patient Found!\n";
            cout << "ID: " << temp->id << endl;
            cout << "Name: " << temp->name << endl;
            cout << "Age: " << temp->age << endl;
            cout << "Disease: " << temp->disease << endl;
            return;
        }
        temp = temp->next;
    }

    cout << "Patient not found!\n";
}

// Display All Patients
void displayPatients()
{
    Patient* temp = head;
    
    if (temp == NULL)
    {
        cout << "No patient records available.\n";
        return;
    }

    while (temp != NULL)
    {
        cout << "\nPatient ID: " << temp->id;
        cout << "\nName: " << temp->name;
        cout << "\nAge: " << temp->age;
        cout << "\nDisease: " << temp->disease << endl;
        temp = temp->next;
    }
}

// Main Function
int main()
{
    int choice;
    do
    {
        cout << "\n--- Hospital Management System ---\n";
        cout << "1. Register Patient\n";
        cout << "2. Search Patient\n";
        cout << "3. Display All Patients\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice)
        {
            case 1:
                registerPatient();
                break;

            case 2:
                searchPatient();
                break;

            case 3:
                displayPatients();
                break;

            case 4:
                cout << "Exiting program...\n";
                break;

            default:
                cout << "Invalid choice!\n";
        }
    } while (choice != 4);

    return 0;
}
