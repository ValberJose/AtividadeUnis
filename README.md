// # AtividadeUnis
// Ciclo2 Unis
#include <iostream>

// Definindo a estrutura do nó
struct Node {
    int data;
    Node* next;
};

// Função para inserir um nó no início da lista
void insertAtBeginning(Node** head, int newData) {
    Node* newNode = new Node();
    newNode->data = newData;
    newNode->next = (*head);
    (*head) = newNode;
}

// Função para imprimir a lista
void printList(Node* node) {
    while (node != nullptr) {
        std::cout << node->data << " ";
        node = node->next;
    }
    std::cout << std::endl;
}

int main() {
    Node* head = nullptr;

    insertAtBeginning(&head, 1);
    insertAtBeginning(&head, 2);
    insertAtBeginning(&head, 3);

    std::cout << "Lista Encadeada: ";
    printList(head);

    return 0;
}
