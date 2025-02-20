# Pemrograman Berorientasi Objek (OOP) dengan C++

## 1. Pendahuluan ke C++
C++ adalah bahasa pemrograman yang mendukung pemrograman prosedural dan berorientasi objek. Sebelum masuk ke OOP, kita akan membahas dasar-dasar C++.

### 1.1 Tipe Data
C++ memiliki berbagai tipe data dasar, seperti:
- `int` (bilangan bulat)
- `float` (bilangan desimal)
- `double` (bilangan desimal presisi tinggi)
- `char` (karakter tunggal)
- `bool` (true/false)
- `string` (teks, menggunakan `#include <string>`)

**Contoh Penggunaan Tipe Data:**
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    int umur = 25;
    float tinggi = 175.5;
    char huruf = 'A';
    bool status = true;
    string nama = "Budi";

    cout << "Nama: " << nama << ", Umur: " << umur << " tahun" << endl;
    return 0;
}
```

### 1.2 Struktur Kontrol
C++ mendukung struktur kontrol seperti `if`, `switch`, `for`, `while`, dan `do-while`.

**Contoh If-Else:**
```cpp
int nilai = 80;
if (nilai >= 75) {
    cout << "Lulus";
} else {
    cout << "Tidak Lulus";
}
```

**Contoh Perulangan:**
```cpp
for (int i = 0; i < 5; i++) {
    cout << "Iterasi ke-" << i << endl;
}
```

### 1.3 Fungsi
Fungsi membantu dalam modularisasi kode.

**Contoh Fungsi:**
```cpp
int tambah(int a, int b) {
    return a + b;
}

int main() {
    cout << "Hasil: " << tambah(5, 3) << endl;
    return 0;
}
```

---
## 2. Pendahuluan ke OOP
Object-Oriented Programming (OOP) adalah paradigma pemrograman yang berorientasi pada objek. OOP menggunakan konsep seperti **kelas** dan **objek** untuk memodelkan data dan perilaku dalam program.

### Konsep Dasar OOP:
1. **Encapsulation** - Menyembunyikan detail implementasi dan hanya menampilkan antarmuka yang diperlukan.
2. **Inheritance** - Pewarisan sifat dari satu kelas ke kelas lainnya.
3. **Polymorphism** - Kemampuan suatu fungsi atau metode untuk memiliki banyak bentuk.
4. **Abstraction** - Menyembunyikan detail kompleks dan hanya menampilkan fungsionalitas utama.

## 3. Kelas dan Objek dalam C++
Dalam pemrograman berorientasi objek (OOP), kelas adalah sebuah blueprint atau template yang mendefinisikan data (atribut) dan perilaku (metode) yang dimiliki oleh objek. Sementara itu, objek adalah instance konkret dari kelas yang dibuat di dalam program.

### 3.1 Struktur Dasar Kelas dalam C++
Sebuah kelas dalam C++ dideklarasikan menggunakan kata kunci class, diikuti oleh nama kelas dan sekelompok atribut serta metode.

Sintaks dasar kelas:

```cpp
class NamaKelas {
private:
    // Atribut (data members)
public:
    // Metode (member functions)
};
```

### 3.2 Membuat dan Menggunakan Kelas dan Objek
Mari kita lihat contoh bagaimana mendefinisikan sebuah kelas dan membuat objek dari kelas tersebut.

```cpp
#include <iostream>
using namespace std;

class Mahasiswa {
public:
    // Atribut
    string nama;
    int umur;

    // Method (fungsi dalam kelas)
    void perkenalan() {
        cout << "Halo, nama saya " << nama << " dan saya berusia " << umur << " tahun." << endl;
    }
};

int main() {
    // Membuat objek dari kelas Mahasiswa
    Mahasiswa mhs1;

    // Mengisi atribut objek
    mhs1.nama = "Budi";
    mhs1.umur = 20;

    // Memanggil metode
    mhs1.perkenalan();

    return 0;
}
```

Penjelasan kode:

1. Mendeklarasikan kelas Mahasiswa dengan dua atribut (nama dan umur) serta satu metode (perkenalan()).
2. Membuat objek mhs1 dari kelas Mahasiswa.
3. Mengisi atribut objek dengan nilai.
4. Memanggil metode untuk mencetak informasi mahasiswa ke layar.

### 3.3 Akses Modifier dalam Kelas
Dalam C++, ada tiga jenis aksesibilitas untuk anggota kelas:

1. private → Hanya bisa diakses dari dalam kelas itu sendiri.
2. public → Bisa diakses dari luar kelas.
3. protected → Hanya bisa diakses oleh kelas itu sendiri dan turunannya (digunakan dalam inheritance).

Contoh Akses Modifier
```cpp
#include <iostream>
using namespace std;

class Mahasiswa {
private:
    string nama; // Hanya bisa diakses dalam kelas ini

public:
    void setNama(string n) { 
        nama = n; 
    }

    string getNama() { 
        return nama; 
    }
};

int main() {
    Mahasiswa mhs1;
    mhs1.setNama("Siti");
    cout << "Nama Mahasiswa: " << mhs1.getNama() << endl;
    return 0;
}
```

Penjelasan:

1. nama bersifat private, jadi tidak bisa diakses langsung dari main().
2. Untuk mengubah dan mengambil nilai nama, digunakan getter (getNama()) dan setter (setNama()).

### 3.4 Constructor dan Destructor

#### Constructor
Constructor adalah metode khusus yang otomatis dipanggil saat objek dibuat. Nama constructor harus sama dengan nama kelas dan tidak memiliki tipe kembalian.

Contoh Constructor:

```cpp
#include <iostream>
using namespace std;

class Mahasiswa {
public:
    string nama;
    int umur;

    // Constructor
    Mahasiswa(string n, int u) {
        nama = n;
        umur = u;
        cout << "Objek mahasiswa telah dibuat!" << endl;
    }

    void tampilkanData() {
        cout << "Nama: " << nama << ", Umur: " << umur << " tahun." << endl;
    }
};

int main() {
    Mahasiswa mhs1("Andi", 21);
    mhs1.tampilkanData();
    return 0;
}
```

#### Destructor
Destructor adalah metode khusus yang dipanggil secara otomatis ketika objek dihancurkan atau keluar dari scope.

Contoh Destructor:

```cpp
class Mahasiswa {
public:
    string nama;

    // Constructor
    Mahasiswa(string n) { nama = n; }

    // Destructor
    ~Mahasiswa() {
        cout << "Objek mahasiswa " << nama << " telah dihancurkan." << endl;
    }
};

int main() {
    Mahasiswa mhs1("Lina");
    return 0;
}
```

Instansiasi Banyak Objek
Satu kelas bisa digunakan untuk membuat banyak objek dengan atribut berbeda.


```cpp
#include <iostream>
using namespace std;

class Mobil {
public:
    string merk;
    int tahun;

    void info() {
        cout << "Mobil " << merk << ", tahun " << tahun << endl;
    }
};

int main() {
    Mobil mobil1, mobil2;

    mobil1.merk = "Toyota";
    mobil1.tahun = 2020;

    mobil2.merk = "Honda";
    mobil2.tahun = 2019;

    mobil1.info();
    mobil2.info();

    return 0;
}
Output:
```

```yaml
Mobil Toyota, tahun 2020
Mobil Honda, tahun 2019
```

## 4. Encapsulation
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

## 5. Inheritance (Pewarisan)
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

## 6. Polymorphism
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

## 7. Abstraction
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

## 8. Kesimpulan
- C++ memiliki dasar seperti tipe data, struktur kontrol, dan fungsi sebelum masuk ke OOP.
- OOP membantu dalam pengorganisasian kode dan meningkatkan reusability.
- C++ menyediakan fitur seperti kelas, objek, pewarisan, dan polymorphism untuk mendukung OOP.
- Dengan memahami konsep OOP, kita dapat membuat program yang lebih modular dan mudah dikelola.
