# Metodo-ordenamiento
#include <iostream>

using namespace std;

void intercambiar(int& a, int& b) {
    int temp = a;
    a = b;
    b = temp;
}

void ordenamientoBurbuja(int arr[], int n, bool ascendente) {
    for (int i = 0; i < n - 1; ++i) {
        for (int j = 0; j < n - 1 - i; ++j) {
            if (ascendente) {
                if (arr[j] > arr[j + 1]) {
                    intercambiar(arr[j], arr[j + 1]);
                }
            } else {
                if (arr[j] < arr[j + 1]) {
                    intercambiar(arr[j], arr[j + 1]);
                }
            }
        }
    }
}

int main() {
    int arreglo[10];
    cout << "Ingrese 10 valores enteros separados por espacios: ";
    for (int i = 0; i < 10; ++i) {
        cin >> arreglo[i];
    }

    char tipo;
    cout << "¿Desea ordenar en orden ascendente (A) o descendente (D)?: ";
    cin >> tipo;

    bool ascendente = (tipo == 'A' || tipo == 'a');

    ordenamientoBurbuja(arreglo, 10, ascendente);

    cout << "Arreglo ordenado: ";
    for (int i = 0; i < 10; ++i) {
        cout << arreglo[i] << " ";
    }
    cout << endl;

    return 0;
}
