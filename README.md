# Object-Oriented Programming (OOP) dengan C++

## 1. Pendahuluan ke OOP
Object-Oriented Programming (OOP) adalah paradigma pemrograman yang berorientasi pada objek. OOP menggunakan konsep seperti **kelas** dan **objek** untuk memodelkan data dan perilaku dalam program.

### Konsep Dasar OOP:
1. **Encapsulation** - Menyembunyikan detail implementasi dan hanya menampilkan antarmuka yang diperlukan.
2. **Inheritance** - Pewarisan sifat dari satu kelas ke kelas lainnya.
3. **Polymorphism** - Kemampuan suatu fungsi atau metode untuk memiliki banyak bentuk.
4. **Abstraction** - Menyembunyikan detail kompleks dan hanya menampilkan fungsionalitas utama.

## 2. Kelas dan Objek dalam C++
Kelas adalah blueprint dari objek. Objek adalah instance dari kelas.

### Contoh Kelas dan Objek:
```cpp
#include <iostream>
using namespace std;

class Mahasiswa {
private:
    string nama;
    int umur;

public:
    // Constructor
    Mahasiswa(string n, int u) {
        nama = n;
        umur = u;
    }
    
    // Method untuk menampilkan data
    void tampilkanData() {
        cout << "Nama: " << nama << ", Umur: " << umur << " tahun." << endl;
    }
};

int main() {
    Mahasiswa mhs1("Budi", 20);
    mhs1.tampilkanData();
    return 0;
}
```

## 3. Encapsulation
Encapsulation melindungi data dengan cara mendefinisikan variabel sebagai private dan mengaksesnya melalui method public.

### Contoh Encapsulation:
```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    double saldo;

public:
    BankAccount(double s) { saldo = s; }
    
    void setSaldo(double s) { saldo = s; }
    double getSaldo() { return saldo; }
};

int main() {
    BankAccount akun(1000000);
    cout << "Saldo awal: " << akun.getSaldo() << endl;
    akun.setSaldo(2000000);
    cout << "Saldo setelah update: " << akun.getSaldo() << endl;
    return 0;
}
```

## 4. Inheritance (Pewarisan)
Pewarisan memungkinkan suatu kelas untuk mewarisi sifat dari kelas lain.

### Contoh Pewarisan:
```cpp
#include <iostream>
using namespace std;

class Kendaraan {
public:
    void maju() { cout << "Kendaraan bergerak maju" << endl; }
};

class Mobil : public Kendaraan {
public:
    void klakson() { cout << "Mobil berbunyi klakson!" << endl; }
};

int main() {
    Mobil avanza;
    avanza.maju();
    avanza.klakson();
    return 0;
}
```

## 5. Polymorphism
Polymorphism memungkinkan penggunaan metode dengan nama yang sama tetapi dengan perilaku berbeda.

### Contoh Polymorphism:
```cpp
#include <iostream>
using namespace std;

class Hewan {
public:
    virtual void bersuara() {
        cout << "Hewan mengeluarkan suara" << endl;
    }
};

class Kucing : public Hewan {
public:
    void bersuara() override {
        cout << "Meong!" << endl;
    }
};

int main() {
    Hewan* h = new Kucing();
    h->bersuara();
    delete h;
    return 0;
}
```

## 6. Abstraction
Abstraction memungkinkan kita untuk menyembunyikan detail implementasi dan hanya menampilkan fitur penting.

### Contoh Abstraction dengan Abstract Class:
```cpp
#include <iostream>
using namespace std;

class Bentuk {
public:
    virtual void gambar() = 0; // Pure virtual function
};

class Lingkaran : public Bentuk {
public:
    void gambar() override {
        cout << "Menggambar Lingkaran" << endl;
    }
};

int main() {
    Bentuk* b = new Lingkaran();
    b->gambar();
    delete b;
    return 0;
}
```

## 7. Kesimpulan
- OOP membantu dalam pengorganisasian kode dan meningkatkan reusability.
- C++ menyediakan fitur seperti kelas, objek, pewarisan, dan polymorphism untuk mendukung OOP.
- Dengan memahami konsep OOP, kita dapat membuat program yang lebih modular dan mudah dikelola.
