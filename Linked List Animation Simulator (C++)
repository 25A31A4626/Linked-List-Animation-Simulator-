#include <iostream>
#include <thread>
#include <chrono>

using namespace std;

class Node {
public:
    int data;
    Node* next;

    Node(int value) {
        data = value;
        next = nullptr;
    }
};

class LinkedList {
private:
    Node* head;

    void delay() {
        this_thread::sleep_for(chrono::milliseconds(800));
    }

public:
    LinkedList() {
        head = nullptr;
    }

    void insertEnd(int value) {
        cout << "\nCreating node [" << value << "]...\n";
        delay();

        Node* newNode = new Node(value);

        if (head == nullptr) {
            head = newNode;
            cout << "Inserted as HEAD\n";
            return;
        }

        Node* temp = head;

        while (temp->next != nullptr) {
            temp = temp->next;
        }

        cout << "Connecting last node to new node...\n";
        delay();

        temp->next = newNode;

        cout << "Insertion Complete!\n";
    }

    void display(Node* current = nullptr) {
        cout << "\nHEAD -> ";

        Node* temp = head;

        while (temp != nullptr) {

            if (temp == current)
                cout << "[" << temp->data << "*] -> ";
            else
                cout << "[" << temp->data << "] -> ";

            temp = temp->next;
        }

        cout << "NULL\n";
    }

    void animateTraversal() {

        cout << "\nStarting Traversal...\n";

        Node* temp = head;

        while (temp != nullptr) {

            display(temp);

            cout << "Current Node = "
                 << temp->data << endl;

            delay();

            temp = temp->next;
        }

        cout << "\nTraversal Complete!\n";
    }

    void search(int key) {

        cout << "\nSearching for "
             << key << "...\n";

        Node* temp = head;

        while (temp != nullptr) {

            display(temp);

            if (temp->data == key) {

                cout << "\nFound Node "
                     << key << "!\n";

                return;
            }

            delay();

            temp = temp->next;
        }

        cout << "\nNode Not Found!\n";
    }

    void deleteValue(int value) {

        if (head == nullptr)
            return;

        cout << "\nDeleting "
             << value << "...\n";

        if (head->data == value) {

            Node* del = head;

            display(head);

            delay();

            head = head->next;

            delete del;

            cout << "Deleted Head Node\n";
            return;
        }

        Node* prev = nullptr;
        Node* curr = head;

        while (curr != nullptr &&
               curr->data != value) {

            display(curr);

            delay();

            prev = curr;
            curr = curr->next;
        }

        if (curr == nullptr) {

            cout << "Value not found\n";
            return;
        }

        prev->next = curr->next;

        delete curr;

        cout << "Node Deleted Successfully\n";
    }
};

int main() {

    LinkedList list;

    list.insertEnd(10);
    list.insertEnd(20);
    list.insertEnd(30);
    list.insertEnd(40);

    list.display();

    list.animateTraversal();

    list.search(30);

    list.deleteValue(20);

    list.display();

    return 0;
}
