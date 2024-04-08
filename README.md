// #Atividade Ciclo 3 Unis
// Desculpa o atraso professor! please.
#include <iostream>

struct Node {
    int data;
    Node* left;
    Node* right;
};

// definir a estrutura para criar um novo nó
Node* createNode(int data) {
    Node* newNode = new Node();
    if (!newNode) {
        std::cout << "Erro na alocação de memória\n";
        return nullptr;
    }
    newNode->data = data;
    newNode->left = newNode->right = nullptr;
    return newNode;
}

// aqui o nó será incluso na arvore
Node* insertNode(Node* root, int data) {
    // Se a árvore estiver vazia, atribua um novo nó de endereço ao root
    if (root == nullptr) {
        root = createNode(data);
        return root;
    }

    
    if (data < root->data) {
        root->left = insertNode(root->left, data);
    }
    else {
        root->right = insertNode(root->right, data);
    }

    return root;
}

// imprimir a árvore
void printTree(Node* root) {
    if (root == nullptr)
        return;

    printTree(root->left);
    std::cout << root->data << " ";
    printTree(root->right);
}

int main() {
    Node* root = nullptr;

    root = insertNode(root, 8); // 8 será a raiz da árvore
    insertNode(root, 3);
    insertNode(root, 10);
    insertNode(root, 1);
    insertNode(root, 6);

    std::cout << "Árvore Binária: ";
    printTree(root);

    return 0;
}

