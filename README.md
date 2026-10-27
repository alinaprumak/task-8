# task-8
#include <iostream>
using namespace std;

bool isPrime(int x) {
    if (x < 2)
        return false;

    for (int i = 2; i * i <= x; i++) {
        if (x % i == 0)
            return false;
    }

    return true;
}

int digitSum(int x) {
    int sum = 0;

    while (x > 0) {
        sum += x % 10;
        x /= 10;
    }

    return sum;
}

int reversed(int x) {
    int result = 0;

    while (x > 0) {
        result = result * 10 + x % 10;
        x /= 10;
    }

    return result;
}

int maxOf(const int a[], int size) {
    int maximum = a[0];

    for (int i = 1; i < size; i++) {
        if (a[i] > maximum)
            maximum = a[i];
    }

    return maximum;
}

int main() {
    int n;
    cin >> n;

    int a[100];

    for (int i = 0; i < n; i++) {
        cin >> a[i];
    }

    for (int i = 0; i < n; i++) {
        cout << a[i] << ": ";

        if (isPrime(a[i]))
            cout << "prostyi";
        else
            cout << "ne prostyi";

        cout << ", suma " << digitSum(a[i]);
        cout << ", navpaky " << reversed(a[i]) << '\n';
    }

    cout << "naibilshe " << maxOf(a, n) << '\n';

    return 0;
}
