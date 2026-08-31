#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

Node* head = NULL;

// Insert at beginning
void insertBeginning(int value) {
    Node* newNode = new Node();

    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

// Insert at end
void insertEnd(int value) {
    Node* newNode = new Node();

    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL) {
        head = newNode;
        return;
    }

    Node* temp = head;

    while (temp->next != NULL) {
        temp = temp->next;
    }

    temp->next = newNode;
}

// Insert at position
void insertPosition(int value, int position) {
    if (position == 1) {
        insertBeginning(value);
        return;
    }

    Node* temp = head;

    for (int i = 1; i < position - 1 && temp != NULL; i++) {
        temp = temp->next;
    }

    if (temp == NULL) {
        cout << "Invalid position\n";
        return;
    }

    Node* newNode = new Node();
    newNode->data = value;

    newNode->next = temp->next;
    temp->next = newNode;
}

// Delete from beginning
void deleteBeginning() {
    if (head == NULL) {
        cout << "List is empty\n";
        return;
    }

    Node* temp = head;
    head = head->next;

    delete temp;
}

// Delete from end
void deleteEnd() {
    if (head == NULL) {
        cout << "List is empty\n";
        return;
    }

    if (head->next == NULL) {
        delete head;
        head = NULL;
        return;
    }

    Node* temp = head;

    while (temp->next->next != NULL) {
        temp = temp->next;
    }

    delete temp->next;
    temp->next = NULL;
}

// Delete from position
void deletePosition(int position) {
    if (head == NULL) {
        cout << "List is empty\n";
        return;
    }

    if (position == 1) {
        deleteBeginning();
        return;
    }

    Node* temp = head;

    for (int i = 1; i < position - 1 && temp != NULL; i++) {
        temp = temp->next;
    }

    if (temp == NULL || temp->next == NULL) {
        cout << "Invalid position\n";
        return;
    }

    Node* deleteNode = temp->next;
    temp->next = deleteNode->next;

    delete deleteNode;
}

// Search
void search(int value) {
    Node* temp = head;
    int position = 1;

    while (temp != NULL) {
        if (temp->data == value) {
            cout << "Element found at position " << position << endl;
            return;
        }

        temp = temp->next;
        position++;
    }

    cout << "Element not found\n";
}

// Forward traversal
void forwardTraversal() {
    Node* temp = head;

    while (temp != NULL) {
        cout << temp->data << " ";
        temp = temp->next;
    }

    cout << endl;
}

// Reverse traversal
void reverseTraversal(Node* temp) {
    if (temp == NULL)
        return;

    reverseTraversal(temp->next);
    cout << temp->data << " ";
}

// Recursive traversal
void recursiveTraversal(Node* temp) {
    if (temp == NULL)
        return;

    cout << temp->data << " ";
    recursiveTraversal(temp->next);
}

int main() {

    int choice, value, position;

    do {
        cout << "\n===== SINGLY LINKED LIST =====\n";
        cout << "1. Insert at Beginning\n";
        cout << "2. Insert at End\n";
        cout << "3. Insert at Position\n";
        cout << "4. Delete from Beginning\n";
        cout << "5. Delete from End\n";
        cout << "6. Delete from Position\n";
        cout << "7. Search\n";
        cout << "8. Forward Traversal\n";
        cout << "9. Reverse Traversal\n";
        cout << "10. Recursive Traversal\n";
        cout << "0. Exit\n";

        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {

        case 1:
            cout << "Enter value: ";
            cin >> value;
            insertBeginning(value);
            break;

        case 2:
            cout << "Enter value: ";
            cin >> value;
            insertEnd(value);
            break;

        case 3:
            cout << "Enter value: ";
            cin >> value;

            cout << "Enter position: ";
            cin >> position;

            insertPosition(value, position);
            break;

        case 4:
            deleteBeginning();
            break;

        case 5:
            deleteEnd();
            break;

        case 6:
            cout << "Enter position: ";
            cin >> position;

            deletePosition(position);
            break;

        case 7:
            cout << "Enter value to search: ";
            cin >> value;

            search(value);
            break;

        case 8:
            cout << "Forward Traversal: ";
            forwardTraversal();
            break;

        case 9:
            cout << "Reverse Traversal: ";
            reverseTraversal(head);
            cout << endl;
            break;

        case 10:
            cout << "Recursive Traversal: ";
            recursiveTraversal(head);
            cout << endl;
            break;

        case 0:
            cout << "Program ended.\n";
            break;

        default:
            cout << "Invalid choice!\n";
        }

    } while (choice != 0);

    return 0;
}
