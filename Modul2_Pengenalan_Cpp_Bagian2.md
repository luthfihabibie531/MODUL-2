<div align="center">

# LAPORAN PRAKTIKUM STRUKTUR DATA
## MODUL 2 — PENGENALAN BAHASA C++ (BAGIAN KEDUA)

**Array, Pointer, Function, Parameter Fungsi, dan Prosedur**

<br>

**Disusun oleh:**<br>
[Ahmad Luthfi Habibie] — [109082500190]<br>
Kelas: [S1IF-13-01]

**Dosen Pengampu:** [Rakhmad Maulidi S.Kom., M.Kom.]<br>
**Asisten Praktikum:** [Aedil Risky Ansyah & Shellyn ]

<br>

**PROGRAM STUDI [S1 INFORMATIKA]**<br>
**FAKULTAS [INFORMATIKA]**<br>
**TELKOM UNIVERSITY PURWOKERTO**<br>
**[2026/2027]**

</div>

---

## Daftar Isi

1. [Pendahuluan](#1-pendahuluan)
   - [1.1 Latar Belakang](#11-latar-belakang)
   - [1.2 Tujuan Praktikum](#12-tujuan-praktikum)
   - [1.3 Dasar Teori](#13-dasar-teori)
2. [Guided](#2-guided)
   - [2.1 Array 1 (Satu Dimensi)](#21-array-1-array-satu-dimensi)
   - [2.2 Array 2 (Dua Dimensi)](#22-array-2-array-dua-dimensi)
   - [2.3 Array 3 (Tiga Dimensi)](#23-array-3-array-tiga-dimensi)
   - [2.4 Array 4 (Empat Dimensi)](#24-array-4-array-empat-dimensi)
   - [2.5 Pointer 1](#25-pointer-1)
   - [2.6 Pointer 2](#26-pointer-2)
   - [2.7 Pointer 3](#27-pointer-3)
   - [2.8 Pointer 4](#28-pointer-4)
   - [2.9 Function](#29-function)
   - [2.10 Parameter Fungsi](#210-parameter-fungsi)
   - [2.11 Prosedur](#211-prosedur)
3. [Unguided](#3-unguided)
   - [3.1 Soal 1 — Operasi Matriks 3×3](#31-soal-1--operasi-matriks-33)
   - [3.2 Soal 2 — Menukar Tiga Variabel](#32-soal-2--menukar-tiga-variabel-dengan-pointer-dan-reference)
   - [3.3 Soal 3 — Menu Nilai Minimum, Maksimum, dan Rata-rata](#33-soal-3--menu-nilai-minimum-maksimum-dan-rata-rata)
4. [Kesimpulan](#4-kesimpulan)
5. [Penutup](#5-penutup)
6. [Daftar Pustaka](#6-daftar-pustaka)

---

## 1. Pendahuluan

### 1.1 Latar Belakang

Mata kuliah Struktur Data membahas cara data disimpan, diatur, dan diakses di dalam memori komputer agar program berjalan efisien. Sebelum masuk ke struktur data yang lebih kompleks seperti *linked list*, *stack*, *queue*, dan *tree*, mahasiswa perlu menguasai dulu konsep dasar pemrograman yang menjadi fondasinya, yaitu *array*, *pointer*, fungsi, dan prosedur. Bahasa C++ dipilih karena memberikan kontrol langsung terhadap memori, sehingga hubungan antara variabel, alamat memori, dan nilai yang tersimpan dapat dipelajari secara nyata.

Modul 2 bagian kedua ini melanjutkan pengenalan bahasa C++ dari modul sebelumnya. Pembahasannya mencakup array satu sampai empat dimensi, pointer beserta operator alamat (`&`) dan dereferensi (`*`), pembuatan fungsi dan prosedur, serta tiga cara melewatkan parameter ke fungsi: *call by value*, *call by pointer*, dan *call by reference*. Seluruh materi dipraktikkan lewat latihan terbimbing (*guided*) dan latihan mandiri (*unguided*).

### 1.2 Tujuan Praktikum

Setelah menyelesaikan praktikum ini, mahasiswa diharapkan mampu:

1. Mendeklarasikan, mengisi, dan mengakses array satu, dua, tiga, dan empat dimensi.
2. Menjelaskan fungsi operator alamat (`&`) dan operator dereferensi (`*`) pada pointer.
3. Membuat dan memanggil fungsi yang mengembalikan nilai serta prosedur yang tidak mengembalikan nilai.
4. Membedakan perilaku *call by value*, *call by pointer*, dan *call by reference*.
5. Menerapkan array, pointer, dan fungsi untuk menyelesaikan persoalan sederhana seperti operasi matriks dan pencarian nilai ekstrem.

### 1.3 Dasar Teori

**Array.** Array adalah variabel yang menyimpan sekumpulan data bertipe sama dalam lokasi memori yang berurutan, dan setiap elemennya diakses melalui indeks yang dimulai dari 0 (Hasibuan dkk., 2023; Putra dkk., 2022). Array dapat memiliki lebih dari satu dimensi. Array dua dimensi dipakai untuk merepresentasikan matriks, sedangkan array tiga dimensi atau lebih menambahkan indeks untuk setiap dimensi tambahannya.

**Pointer.** Pointer adalah variabel yang tidak menyimpan nilai data secara langsung, melainkan menyimpan alamat memori dari variabel lain (Rianto, 2026). Operator `&` menghasilkan alamat suatu variabel, sedangkan operator `*` yang dipakai pada pointer mengambil nilai yang tersimpan pada alamat tersebut. Pointer memungkinkan sebuah fungsi mengubah variabel milik pemanggilnya secara langsung.

**Fungsi dan prosedur.** Fungsi adalah blok program bernama yang menerima masukan (parameter) dan mengembalikan satu nilai lewat `return`, sedangkan prosedur adalah blok serupa yang tidak mengembalikan nilai sehingga bertipe `void` (Huda dkk., 2022). Pemisahan program menjadi fungsi dan prosedur membuat kode lebih terstruktur dan dapat dipakai ulang.

**Parameter fungsi.** Pada *call by value*, fungsi hanya menerima salinan nilai sehingga perubahan di dalam fungsi tidak memengaruhi variabel asli. Pada *call by pointer*, fungsi menerima alamat variabel dan mengubah nilainya melalui dereferensi. Pada *call by reference*, fungsi menerima referensi (nama lain) dari variabel asli sehingga perubahan langsung berlaku tanpa sintaks pointer.

---

## 2. Guided

Pada bagian *guided*, setiap program ditampilkan lengkap dengan kodenya, kemudian dijelaskan cara kerjanya dalam bentuk paragraf.

### 2.1 Array 1 (Array Satu Dimensi)


```cpp
#include <iostream>
using namespace std;
int main() {
    int nilai[5];
    nilai[0] = 80;
    nilai[1] = 85;
    nilai[2] = 90;
    nilai[3] = 75;
    nilai[4] = 95;
    for (int i = 0; i < 5; i++) {
        cout << "index ke-" << i << " = " << nilai[i] << endl;
    }
    return 0;
}
```

Program ini mendeklarasikan array satu dimensi bernama `nilai` bertipe `int` dengan lima elemen. Tiap elemen diisi satu per satu lewat indeksnya, yaitu `nilai[0]` sampai `nilai[4]`, dengan nilai 80, 85, 90, 75, dan 95. Karena indeks array selalu dimulai dari 0, elemen terakhir dari array berukuran lima berada pada indeks 4, bukan 5. Setelah pengisian, perulangan `for` berjalan dari `i = 0` hingga `i < 5` untuk mencetak setiap elemen bersama nomor indeksnya dengan format `index ke-i = nilai`. Perulangan ini menunjukkan pola umum penelusuran array, yaitu satu variabel penghitung yang dipakai sebagai indeks.

### 2.2 Array 2 (Array Dua Dimensi)


```cpp
#include <iostream>
using namespace std;
int main() {
    int nilai[3][3] = {
        {80, 85, 90},
        {75, 80, 85},
        {90, 95, 100}
    };
    cout << nilai[0][0] << endl; //80
    cout << nilai[1][1] << endl; //80
    cout << nilai[2][2] << " "; //100
    return 0;
}
```

Program ini memakai array dua dimensi `nilai[3][3]` yang dapat dibayangkan sebagai tabel atau matriks berukuran 3 baris dan 3 kolom. Seluruh isinya langsung diberikan saat deklarasi menggunakan kurung kurawal bersarang, dengan satu pasang kurung kurawal untuk setiap baris. Elemen diakses dengan format `nilai[baris][kolom]`. Program mencetak `nilai[0][0]` (baris pertama kolom pertama, bernilai 80), `nilai[1][1]` (baris kedua kolom kedua, bernilai 80), dan `nilai[2][2]` (baris ketiga kolom ketiga, bernilai 100). Ketiganya adalah elemen pada diagonal utama matriks. Dua nilai pertama dicetak dengan `endl` sehingga turun baris, sedangkan nilai terakhir dicetak diikuti spasi tanpa pindah baris.

### 2.3 Array 3 (Array Tiga Dimensi)


```cpp
#include <iostream>
using namespace std;
int main() {
    int data[2][3][3] = {
        {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        },
        {
            {10, 11, 12},
            {13, 14, 15},
            {16, 17, 18}
        }
    };
    cout << data[0][1][1] << " "; // 5
    return 0;
}
```

Array `data[2][3][3]` memiliki tiga indeks. Cara paling mudah memahaminya adalah membayangkan dua lapisan (blok), yang masing-masing berisi matriks 3×3. Lapisan pertama berisi angka 1 sampai 9 dan lapisan kedua berisi angka 10 sampai 18. Indeks pertama memilih lapisan, indeks kedua memilih baris, dan indeks ketiga memilih kolom. Ekspresi `data[0][1][1]` berarti lapisan pertama, baris kedua, kolom kedua, yaitu angka 5, sehingga program mencetak 5. Pola inilah yang membuat jumlah kurung kurawal pada inisialisasi harus sesuai dengan jumlah dimensi array.

### 2.4 Array 4 (Array Empat Dimensi)


```cpp
#include <iostream>
using namespace std;
int main() {
    int data[2][2][2][2] = {
        {
            {
                {1, 2},
                {3, 4}
            },
            {
                {5, 6},
                {7, 8}
            }
        },
        {
            {
                {9, 10},
                {11, 12}
            },
            {
                {13, 14},
                {15, 16}
            }
        }
    };
    cout << data[0][0][0][0] << endl; // 1
    cout << data[1][1][1][1] << endl; //16
    return 0;
}
```

Array `data[2][2][2][2]` adalah array empat dimensi yang menyimpan 2 × 2 × 2 × 2 = 16 elemen, diisi dengan angka 1 sampai 16 secara berurutan. Struktur kurung kurawalnya bersarang empat tingkat, mengikuti urutan dimensi dari yang terluar sampai yang terdalam. Program mencetak `data[0][0][0][0]` yang merupakan elemen paling awal (bernilai 1) dan `data[1][1][1][1]` yang merupakan elemen paling akhir (bernilai 16). Contoh ini memperlihatkan bahwa C++ dapat menangani array dengan dimensi berapa pun, tetapi semakin banyak dimensi, semakin sulit pula array dibayangkan dan dibaca.

### 2.5 Pointer 1


```cpp
#include <iostream>
using namespace std;
int main() {
    char a;
    int j;
    char arr[6];
    arr[3] = 'b';
    a = 'u';
    j = 10;
    cout << a << endl; //u
    cout << &a << endl; //alamat memory atau address
    cout << j << endl; //10
    cout << &j << endl; //alamat memory atau address
    cout << arr[3] << endl; //value
    cout << &(arr[4]) << endl; //alamat memory atau address
    return 0;
}
```

Program ini memperkenalkan operator alamat `&` yang menghasilkan lokasi sebuah variabel di memori. Terdapat variabel `a` bertipe `char` (diisi `'u'`), variabel `j` bertipe `int` (diisi 10), dan array karakter `arr` berukuran 6 yang hanya elemen ke-3 nya diisi `'b'`. Pencetakan `a`, `j`, dan `arr[3]` menampilkan nilai masing-masing, sedangkan `&j` menampilkan alamat memori `j` dalam bentuk heksadesimal. Ada satu hal yang perlu diperhatikan: ketika `&a` dan `&(arr[4])` dikirim ke `cout`, tipenya adalah `char*`, dan C++ memperlakukannya sebagai *string* ala C, bukan sebagai alamat. Akibatnya `cout` mencetak karakter mulai dari alamat itu sampai bertemu karakter `'\0'`, sehingga hasilnya dapat berupa karakter tambahan yang tidak terduga dan bisa berbeda di setiap komputer atau setiap kali program dijalankan, apalagi `arr[4]` belum pernah diisi. Untuk benar-benar menampilkan alamat sebuah `char`, nilainya perlu dikonversi dulu, misalnya dengan `static_cast<void*>(&a)`.

### 2.6 Pointer 2


```cpp
#include <iostream>
using namespace std;
int main() {
    int x, y;
    int *px;
    x = 87;
    px = &x;
    y = *px;
    cout << "Alamat x= " << &x << endl;
    cout << "Isi px= " << px << endl;
    cout << "Isi X= " << x << endl;
    cout << "Nilai yang ditunjuk px= " << *px << endl;
    cout << "Nilai y= " << y << endl;
    return 0;
}
```

Program ini menunjukkan pointer yang sebenarnya. Variabel `px` dideklarasikan sebagai `int *px`, yaitu pointer yang dapat menyimpan alamat sebuah `int`. Setelah `x` diisi 87, perintah `px = &x` membuat `px` menunjuk ke `x`, sehingga isi `px` sama dengan alamat `x`. Perintah `y = *px` memakai operator dereferensi untuk mengambil nilai yang ditunjuk `px`, yaitu 87, lalu menyalinnya ke `y`. Program mencetak lima baris: alamat `x`, isi `px` (alamat yang sama dengan sebelumnya), isi `x` (87), nilai yang ditunjuk `px` (87), dan nilai `y` (87). Alamat memori yang tampil akan berbeda setiap kali program dijalankan karena ditentukan oleh sistem operasi, tetapi dua baris pertama selalu sama nilainya.

### 2.7 Pointer 3


```cpp
#include <iostream>
#define MAX 5
using namespace std;

int main() {
    int i, j;
    float nilai_total, rata_rata;
    float nilai[MAX];
    static int nilai_tahun[MAX][MAX] = {
        {0, 2, 2, 0, 0},
        {0, 1, 1, 1, 0},
        {0, 3, 3, 3, 0},
        {4, 4, 0, 0, 4},
        {5, 0, 0, 0, 5}
    };

    // inisialisasi array satu dimensi
    for (i = 0; i < MAX; i++) {
        cout << "masukkan nilai ke-" << i + 1 << endl;
        cin >> nilai[i];
    }

    cout << "\ndata nilai siswa :\n";
    // menampilkan array satu dimensi
    for (i = 0; i < MAX; i++)
        cout << "nilai k-" << i + 1 << "=" << nilai[i] << endl;

    cout << "\n nilai tahunan : \n";
    // menampilkan array dua dimensi
    for (i = 0; i < MAX; i++) {
        for (j = 0; j < MAX; j++)
            cout << nilai_tahun[i][j];
        cout << "\n";
    }

    return 0;
}
```

Program ini memakai konstanta `MAX` yang didefinisikan dengan `#define` sebagai 5, sehingga ukuran array dapat diubah cukup di satu tempat. Ada dua array: `nilai` yang berupa array satu dimensi bertipe `float` dan diisi dari masukan pengguna lewat `cin` di dalam perulangan, serta `nilai_tahun` yang berupa array dua dimensi 5×5 bertipe `int` dengan kata kunci `static` dan sudah berisi data awal. Bagian pertama meminta lima nilai dan mencetaknya kembali dengan format `nilai k-i=...`. Bagian kedua mencetak isi `nilai_tahun` dengan dua perulangan bersarang, perulangan luar untuk baris dan perulangan dalam untuk kolom, lalu pindah baris setiap satu baris selesai dicetak. Variabel `nilai_total` dan `rata_rata` sudah dideklarasikan tetapi belum dipakai pada program ini, jadi dapat dimanfaatkan jika ingin dikembangkan untuk menghitung rata-rata.

### 2.8 Pointer 4


```cpp
#include <iostream>
using namespace std;
int main() {
    char nama[] = "strukdat";
    cout << nama << endl;
    cout << nama[3] << endl;
    return 0;
}
```

Program ini mengenalkan hubungan antara array karakter dan string. Deklarasi `char nama[] = "strukdat"` membuat array karakter yang ukurannya otomatis menyesuaikan, yaitu 9 elemen: delapan huruf ditambah satu karakter penutup `'\0'` yang ditambahkan compiler secara otomatis. Perintah `cout << nama` mencetak seluruh isi string hingga karakter penutup, sehingga tampil `strukdat`. Perintah `cout << nama[3]` mencetak elemen berindeks 3, yaitu huruf `u` (urutannya s-t-r-u-k-d-a-t, dengan indeks dimulai dari 0). Perlu diingat bahwa nama array pada dasarnya menunjuk ke alamat elemen pertamanya, itulah alasan array dan pointer sering dibahas bersamaan.

### 2.9 Function


```cpp
#include <iostream>
using namespace std;
int maks3(int a, int b, int c);
int main() {
    int x, y, z;
    cout << "Masukkan nilai bilangan ke-1 = ";
    cin >> x;
    cout << "Masukkan nilai bilangan ke-2 = ";
    cin >> y;
    cout << "Masukkan nilai bilangan ke-3 = ";
    cin >> z;
    cout << "Nilai maksimumnya adalah = " << maks3(x, y, z);
    return 0;
}
int maks3(int a, int b, int c) {
    int temp_max = a;
    if (b > temp_max)
        temp_max = b;
    if (c > temp_max)
        temp_max = c;
    return temp_max;
}
```

Program ini mendemonstrasikan fungsi yang mengembalikan nilai. Fungsi `maks3` dideklarasikan lebih dulu sebagai *prototype* di atas `main()`, lalu didefinisikan di bawahnya. Di dalam `main()`, pengguna memasukkan tiga bilangan ke `x`, `y`, dan `z`, kemudian ketiganya dikirim ke `maks3`. Di dalam fungsi, variabel `temp_max` diawali dengan nilai `a`, lalu dibandingkan dengan `b` dan `c`; setiap kali ada nilai yang lebih besar, `temp_max` diperbarui. Hasil akhirnya dikembalikan dengan `return temp_max` dan dicetak oleh `main()`. Pendekatan ini hanya memerlukan dua kali perbandingan untuk menentukan nilai terbesar dari tiga bilangan.

### 2.10 Parameter Fungsi


```cpp
#include <iostream>
using namespace std;
void tukarValue(int x, int y) {
    int temp = x;
    x = y;
    y = temp;
}
void tukarPointer(int *x, int *y) {
    int temp = *x;
    *x = *y;
    *y = temp;
}
void tukarReference(int &x, int &y) {
    int temp = x;
    x = y;
    y = temp;
}
int main() {
    int a = 4, b = 6;
    tukarValue(a, b);
    cout << "Setelah Call by Value -> a = " << a << ", b = " << b << " (Tetap)" << endl;
    tukarPointer(&a, &b);
    cout << "Setelah Call by Pointer -> a = " << a << ", b = " << b << " (Berubah!)" << endl;
    tukarReference(a, b);
    cout << "Setelah Call by Reference -> a = " << a << ", b = " << b << " (Berubah lagi!)" << endl;
    return 0;
}
```

Program ini membandingkan tiga cara melewatkan parameter dengan tujuan yang sama, yaitu menukar dua nilai. Pada `tukarValue`, parameter `x` dan `y` hanyalah salinan, jadi pertukaran yang terjadi di dalam fungsi tidak mengubah `a` dan `b` di `main()`; nilainya tetap 4 dan 6. Pada `tukarPointer`, fungsi menerima alamat (`int *x`, `int *y`) dan menukar isi melalui dereferensi `*x` dan `*y`, sehingga `a` dan `b` benar-benar tertukar menjadi 6 dan 4. Pada `tukarReference`, parameter `int &x` dan `int &y` adalah nama lain dari variabel asli, sehingga penukaran langsung berlaku tanpa tanda `*` maupun `&` saat pemanggilan. Karena `tukarReference` dipanggil setelah `tukarPointer`, nilai ditukar sekali lagi sehingga `a` dan `b` kembali menjadi 4 dan 6. Dari tiga cara ini, *call by value* adalah satu-satunya yang tidak dapat dipakai untuk mengubah variabel milik pemanggil.

### 2.11 Prosedur


```cpp
#include <iostream>
using namespace std;
void tulis(int x);
int main() {
    int jum;
    cout << "jumlah baris kata = ";
    cin >> jum;
    tulis(jum);
    return 0;
}
void tulis(int x) {
    for (int i = 0; i < x; i++)
        cout << "baris ke-" << i + 1 << endl;
}
```

Prosedur adalah fungsi yang tidak mengembalikan nilai, sehingga bertipe `void`. Prosedur `tulis` menerima satu parameter `x` yang menyatakan berapa kali sebuah baris akan dicetak. Pada `main()`, pengguna memasukkan jumlah baris lewat variabel `jum`, kemudian `tulis(jum)` dipanggil. Di dalam prosedur, perulangan `for` mencetak teks `baris ke-` diikuti nomor urut yang dimulai dari 1 (dihasilkan dari `i + 1`, karena `i` sendiri dimulai dari 0). Karena hanya bertugas menampilkan sesuatu ke layar, prosedur tidak memerlukan `return`, berbeda dengan fungsi `maks3` pada bagian sebelumnya.

---

## 3. Unguided

Pada bagian *unguided*, setiap soal dilengkapi kode program, penjelasan, dan output program. Baris yang diketik pengguna ditampilkan bersama output agar alur interaksinya terlihat jelas.

### 3.1 Soal 1 — Operasi Matriks 3×3

**Deskripsi soal:** Membuat program yang menerima dua matriks berordo 3×3 dari pengguna, kemudian menampilkan hasil penjumlahan, pengurangan, dan perkalian kedua matriks tersebut.

**Kode program:**


```cpp
#include <iostream>
using namespace std;
int main() {
    int A[3][3], B[3][3];
    int jumlah[3][3];
    int kurang[3][3];
    int kali[3][3];
    cout << "Masukkan matriks A:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cin >> A[i][j];
        }
    }
    cout << "Masukkan matriks B:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cin >> B[i][j];
        }
    }
    // Penjumlahan matriks
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            jumlah[i][j] = A[i][j] + B[i][j];
        }
    }
    // Pengurangan matriks
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            kurang[i][j] = A[i][j] - B[i][j];
        }
    }
    // Perkalian matriks
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            kali[i][j] = 0;
            for (int k = 0; k < 3; k++) {
                kali[i][j] += A[i][k] * B[k][j];
            }
        }
    }
    cout << "\nHasil Penjumlahan:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << jumlah[i][j] << " ";
        }
        cout << endl;
    }
    cout << "\nHasil Pengurangan:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << kurang[i][j] << " ";
        }
        cout << endl;
    }
    cout << "\nHasil Perkalian:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << kali[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Penjelasan:**

Program menyiapkan lima array dua dimensi berukuran 3×3: `A` dan `B` untuk masukan, serta `jumlah`, `kurang`, dan `kali` untuk hasil. Masukan matriks `A` dan `B` dibaca elemen per elemen dengan dua perulangan `for` bersarang, perulangan luar untuk baris `i` dan perulangan dalam untuk kolom `j`. Penjumlahan dan pengurangan dilakukan dengan cara yang paling sederhana, yaitu menjumlahkan atau mengurangkan elemen yang berposisi sama, `A[i][j] ± B[i][j]`. Perkalian matriks lebih rumit karena memerlukan tiga perulangan bersarang. Untuk setiap elemen hasil `kali[i][j]`, nilainya diawali 0 lalu ditambah hasil kali elemen baris ke-`i` pada `A` dengan elemen kolom ke-`j` pada `B`, yaitu `A[i][k] * B[k][j]` untuk `k` dari 0 sampai 2. Setelah semua operasi selesai, ketiga hasil dicetak dengan perulangan bersarang yang sama.

Sebagai contoh, dengan `A` berisi angka 1 sampai 9 dan `B` berisi angka 9 sampai 1, elemen pertama hasil perkalian dihitung (1×9) + (2×6) + (3×3) = 30. Hasil ini sesuai dengan output program.

output program [Cuplikan layar 2026-10-05 232545.png]
**Output program:**

```text
Masukkan matriks A:
1 2 3
4 5 6
7 8 9
Masukkan matriks B:
9 8 7
6 5 4
3 2 1

Hasil Penjumlahan:
10 10 10 
10 10 10 
10 10 10 

Hasil Pengurangan:
-8 -6 -4 
-2 0 2 
4 6 8 

Hasil Perkalian:
30 24 18 
84 69 54 
138 114 90 
```

### 3.2 Soal 2 — Menukar Tiga Variabel dengan Pointer dan Reference

**Deskripsi soal:** Membuat program yang menerima tiga bilangan `a`, `b`, dan `c`, lalu menukar nilainya secara melingkar menggunakan fungsi berparameter pointer dan fungsi berparameter reference.

**Kode program:**


```cpp
#include <iostream>
using namespace std;
void tukarPointer(int *a, int *b, int *c) {
    int temp;
    temp = *a;
    *a = *b;
    *b = *c;
    *c = temp;
}
void tukarReference(int &a, int &b, int &c) {
    int temp;
    temp = a;
    a = b;
    b = c;
    c = temp;
}
int main() {
    int a, b, c;
    cout << "Masukkan nilai a : ";
    cin >> a;
    cout << "Masukkan nilai b : ";
    cin >> b;
    cout << "Masukkan nilai c : ";
    cin >> c;
    cout << "\nSebelum ditukar:" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
    cout << "c = " << c << endl;
    tukarPointer(&a, &b, &c);
    cout << "\nSetelah ditukar menggunakan pointer:" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
    cout << "c = " << c << endl;
    tukarReference(a, b, c);
    cout << "\nSetelah ditukar kembali menggunakan reference:" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
    cout << "c = " << c << endl;
    return 0;
}
```

**Penjelasan:**

Program memiliki dua fungsi dengan logika yang sama tetapi cara melewatkan parameter yang berbeda. Fungsi `tukarPointer` menerima tiga alamat (`int *a, int *b, int *c`) dan bekerja dengan dereferensi: nilai `*a` disimpan sementara di `temp`, `*a` diisi `*b`, `*b` diisi `*c`, lalu `*c` diisi `temp`. Fungsi `tukarReference` melakukan langkah yang sama, tetapi parameternya bertipe referensi (`int &a, int &b, int &c`) sehingga di dalam fungsi variabel dipakai langsung tanpa tanda `*`. Dari `main()`, pointer dipanggil dengan `tukarPointer(&a, &b, &c)` yang mengirim alamat, sedangkan reference dipanggil dengan `tukarReference(a, b, c)` yang mengirim variabelnya langsung.

Pertukaran ini berupa perputaran nilai, bukan pembalikan: `a` menerima nilai `b`, `b` menerima nilai `c`, dan `c` menerima nilai `a` yang lama. Oleh sebab itu, pemanggilan fungsi kedua tidak mengembalikan nilai ke kondisi awal, melainkan memutarnya sekali lagi. Pada contoh masukan 10, 20, 30, hasil setelah pointer adalah 20, 30, 10, dan setelah reference menjadi 30, 10, 20. Nilai awal baru akan kembali setelah tiga kali putaran. Meskipun hasil akhirnya sama, kedua fungsi membuktikan bahwa pointer dan reference sama-sama dapat mengubah variabel asli di luar fungsi.

**Output program:**

```text
Masukkan nilai a : 10
Masukkan nilai b : 20
Masukkan nilai c : 30

Sebelum ditukar:
a = 10
b = 20
c = 30

Setelah ditukar menggunakan pointer:
a = 20
b = 30
c = 10

Setelah ditukar kembali menggunakan reference:
a = 30
b = 10
c = 20
```

### 3.3 Soal 3 — Menu Nilai Minimum, Maksimum, dan Rata-rata

**Deskripsi soal:** Membuat program berbasis menu yang bekerja pada array `arrA` berisi 10 bilangan `{11, 8, 5, 7, 12, 26, 3, 54, 33, 55}`. Menu menyediakan pilihan untuk mencari nilai minimum, nilai maksimum, dan nilai rata-rata, masing-masing dengan fungsi tersendiri.

**Kode program:**


```cpp
#include <iostream>
using namespace std;
int cariMinimum(int arr[], int n) {
    int min = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] < min) {
            min = arr[i];
        }
    }
    return min;
}
int cariMaksimum(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    return max;
}
float hitungRataRata(int arr[], int n) {
    int total = 0;
    for (int i = 0; i < n; i++) {
        total += arr[i];
    }
    return (float) total / n;
}
int main() {
    int arrA[10] = {11, 8, 5, 7, 12, 26, 3, 54, 33, 55};
    int pilihan;
    cout << "Data Array:" << endl;
    for (int i = 0; i < 10; i++) {
        cout << arrA[i] << " ";
    }
    cout << endl;
    cout << "\n===== MENU =====" << endl;
    cout << "1. Cari Minimum" << endl;
    cout << "2. Cari Maksimum" << endl;
    cout << "3. Hitung Rata-rata" << endl;
    cout << "4. Keluar" << endl;
    cout << "\nPilih menu: ";
    cin >> pilihan;
    switch (pilihan) {
        case 1:
            cout << "Nilai minimum = "
                 << cariMinimum(arrA, 10) << endl;
            break;
        case 2:
            cout << "Nilai maksimum = "
                 << cariMaksimum(arrA, 10) << endl;
            break;
        case 3:
            cout << "Nilai rata-rata = "
                 << hitungRataRata(arrA, 10) << endl;
            break;
        case 4:
            cout << "Program selesai." << endl;
            break;
        default:
            cout << "Pilihan tidak tersedia." << endl;
    }
    return 0;
}
```

**Penjelasan:**

Program dibagi menjadi tiga fungsi yang masing-masing menerima array dan jumlah elemennya (`int arr[], int n`). Fungsi `cariMinimum` mengasumsikan elemen pertama sebagai nilai terkecil, lalu menelusuri elemen berikutnya dan mengganti `min` setiap kali ditemukan nilai yang lebih kecil. Fungsi `cariMaksimum` bekerja serupa dengan pembanding terbalik. Fungsi `hitungRataRata` menjumlahkan semua elemen ke variabel `total` kemudian membaginya dengan `n`; hasil bagi diubah dulu menjadi `float` lewat `(float) total / n` agar hasilnya tidak dibulatkan menjadi bilangan bulat. Karena array pada C++ dilewatkan sebagai alamat elemen pertamanya, fungsi bekerja langsung pada array asli tanpa menyalin seluruh isinya.

Di `main()`, program menampilkan isi array, mencetak menu, lalu membaca pilihan pengguna. Struktur `switch` memanggil fungsi yang sesuai: pilihan 1 untuk minimum, 2 untuk maksimum, 3 untuk rata-rata, 4 untuk keluar, dan blok `default` menangani pilihan di luar menu. Perhitungan manual memperkuat hasilnya: nilai terkecil adalah 3, nilai terbesar adalah 55, dan jumlah seluruh elemen adalah 214 sehingga rata-ratanya 214 / 10 = 21,4.

**Output program** (menu tampil sama pada setiap pilihan, dan yang berbeda hanya baris terakhir):

```text
Data Array:
11 8 5 7 12 26 3 54 33 55 

===== MENU =====
1. Cari Minimum
2. Cari Maksimum
3. Hitung Rata-rata
4. Keluar

Pilih menu: 1
Nilai minimum = 3
```

Hasil untuk pilihan menu lainnya:

| Pilihan | Baris terakhir pada output |
|:-------:|----------------------------|
| 1 | `Nilai minimum = 3` |
| 2 | `Nilai maksimum = 55` |
| 3 | `Nilai rata-rata = 21.4` |
| 4 | `Program selesai.` |
| selain 1–4 (misalnya 5) | `Pilihan tidak tersedia.` |

---

## 4. Kesimpulan

Berdasarkan praktikum Modul 2 bagian kedua ini, dapat disimpulkan beberapa hal berikut.

1. **Array** adalah cara menyimpan banyak data bertipe sama secara berurutan dan diakses melalui indeks yang dimulai dari 0. Array dapat berdimensi satu sampai banyak, dan array dua dimensi sangat cocok untuk merepresentasikan matriks seperti pada operasi penjumlahan, pengurangan, dan perkalian matriks di Soal 1.
2. **Pointer** menyimpan alamat memori, bukan nilai. Operator `&` dipakai untuk mengambil alamat, dan operator `*` dipakai untuk mengakses nilai yang ditunjuk. Pemahaman ini menjadi dasar untuk struktur data dinamis seperti *linked list* pada pertemuan berikutnya.
3. **Fungsi** mengembalikan nilai lewat `return`, sedangkan **prosedur** bertipe `void` dan hanya menjalankan serangkaian perintah. Memecah program menjadi fungsi, seperti `cariMinimum`, `cariMaksimum`, dan `hitungRataRata` pada Soal 3, membuat kode lebih rapi, mudah diuji, dan dapat dipakai ulang.
4. **Parameter fungsi** memengaruhi apakah variabel asli berubah. *Call by value* hanya menyalin nilai sehingga variabel asli tetap, sedangkan *call by pointer* dan *call by reference* mengubah variabel asli. Reference memberikan sintaks yang lebih ringkas, sementara pointer memberikan fleksibilitas lebih karena alamatnya dapat diolah langsung.
5. Beberapa hal teknis perlu diwaspadai, misalnya `cout << &variabelChar` yang diperlakukan sebagai string sehingga hasilnya tidak berupa alamat, serta fungsi penukar tiga variabel yang bersifat memutar nilai sehingga tidak otomatis mengembalikan kondisi awal.

Seluruh program pada praktikum ini sudah dikompilasi dan dijalankan, dan keluarannya sesuai dengan penjelasan konsep di atas.

---

## 5. Penutup

Demikian laporan praktikum Struktur Data Modul 2 (Pengenalan Bahasa C++ Bagian Kedua) ini disusun. Penulis berharap laporan ini dapat membantu pembaca memahami konsep array, pointer, fungsi, parameter fungsi, dan prosedur dalam bahasa C++ sebagai bekal untuk materi struktur data pada pertemuan selanjutnya. Penulis menyadari bahwa laporan ini masih memiliki kekurangan, sehingga kritik dan saran yang membangun sangat diharapkan demi perbaikan di masa mendatang. Penulis mengucapkan terima kasih kepada dosen pengampu dan asisten praktikum Telkom University atas bimbingan yang diberikan selama praktikum berlangsung.

---

## 6. Daftar Pustaka

1. Hasibuan, A., Kembuan, D. R. E., & Tinambunan, M. H. (2023). *Buku ajar algoritma dan pemrograman menggunakan bahasa pemrograman C++*. Tahta Media Group. ISBN 978-623-147-131-4. https://tahtamedia.co.id/index.php/issj/article/view/376
2. Huda, A., Ardi, N., & Muabi, A. (2022). *Pengantar coding berbasis C/C++*. UNP Press. https://unppress.unp.ac.id/index.php/unp-press/catalog/book/83
3. Putra, M. T. D., dkk. (2022). *Buku belajar dasar pemrograman dengan C++*. Penerbit Widina. https://store.penerbitwidina.com/product/buku-belajar-dasar-pemrograman-dengan-c/
4. Rianto, I. (2026). *Dasar-dasar pemrograman dengan C++*. Tahta Media Group. ISBN 978-634-262-213-1. https://tahtamedia.co.id/issj/article/view/2051
