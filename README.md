# laba_2

#include <iostream>
#include <time.h>

using namespace std;

void reshenie_kvadratnogo() {
    double a, b, c, x1, x2;
    cout << "Введите a: ";
    cin >> a;
    cout << "Введите b: ";
    cin >> b;
    cout << "Введите c: ";
    cin >> c;
    if ((b * b - 4 * a * c) >= 0) { // Если дискриминант больше или равен 0
        x1 = (-1 * b + sqrt(b * b - 4 * a * c)) / (2 * a);
        cout << "Первый корень равен " << x1 << endl;
        x1 = (-1 * b -sqrt(b * b - 4 * a * c)) / (2 * a);
        cout << "Второй корень равен " << x1 << endl;
    }
    else {
        cout << "Дискриминант меньше 0, корней нет" << endl;
    }
}

void find_random() {
    srand(time(NULL));
    int left, right;
    cout << "Введите левую границу: " << endl;
    cin >> left;
    cout << "Введите правую границу: " << endl;
    do {
        cin >> right;
        if (right < left) cout << "Правая граница должна быть больше левой" << endl;
    } while (right < left);
    int rand_value = left + (rand() % right - left);
    cout << "Случайное число в диапазоне от " << left << " до " << right << ": " << rand_value << endl;
}

void sortirovka_puzirok() {
    int arr[10];
    int temp = 0;

    cout << "Введите элементы массива" << endl;
    for (int i = 0; i < 10; i++) {
        cin >> arr[i];
    }

    for (int i = 0; i < 10; i++) {
        for (int j = 0; j < 9; j++) {
            if (arr[j] > arr[j + 1]) {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }

    cout << "Отсортированный массив" << endl;
    for (int i = 0; i < 10; i++) {
        cout << arr[i] << " ";
    }
}

int main()
{
    setlocale(LC_ALL, "ru");
    reshenie_kvadratnogo();
    find_random();
    sortirovka_puzirok();
}
