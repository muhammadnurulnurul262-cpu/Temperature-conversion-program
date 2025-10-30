# Temperature-conversion-program
hmmmm I don't really understand the C++ programming language. If you want to improve or add something, please do so.


#include <iostream>
#include <iomanip> // Untuk setprecision

using namespace std;

int main() {
    double suhu, hasil;
    char unitAsal, unitTujuan;
    
    cout << "Masukkan suhu: ";
    cin >> suhu;
    
    cout << "Masukkan unit asal (C untuk Celsius, F untuk Fahrenheit, K untuk Kelvin): ";
    cin >> unitAsal;
    
    cout << "Masukkan unit tujuan (C untuk Celsius, F untuk Fahrenheit, K untuk Kelvin): ";
    cin >> unitTujuan;
    
    // Konversi ke Celsius terlebih dahulu
    double celsius;
    if (unitAsal == 'C' || unitAsal == 'c') {
        celsius = suhu;
    } else if (unitAsal == 'F' || unitAsal == 'f') {
        celsius = (suhu - 32) * 5.0 / 9.0;
    } else if (unitAsal == 'K' || unitAsal == 'k') {
        celsius = suhu - 273.15;
    } else {
        cout << "Unit asal tidak valid!" << endl;
        return 1;
    }
    
    // Konversi dari Celsius ke unit tujuan
    if (unitTujuan == 'C' || unitTujuan == 'c') {
        hasil = celsius;
    } else if (unitTujuan == 'F' || unitTujuan == 'f') {
        hasil = (celsius * 9.0 / 5.0) + 32;
    } else if (unitTujuan == 'K' || unitTujuan == 'k') {
        hasil = celsius + 273.15;
    } else {
        cout << "Unit tujuan tidak valid!" << endl;
        return 1;
    }
    
    cout << fixed << setprecision(2);
    cout << "Suhu " << suhu << " " << unitAsal << " adalah " << hasil << " " << unitTujuan << endl;
    
    return 0;
}
