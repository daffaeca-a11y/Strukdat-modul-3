# <h1 align="center">Laporan Praktikum Modul 3 - Abstract Data Type</h1>
<p align="center">Muhammad Daffa Sha'ib Nandana - 109082500023</p>

## Dasar Teori
Abstract Data Type atau ADT adalah sebuah konsep teoretis dalam ilmu komputer yang memodelkan tipe data berdasarkan perilakunya, bukan cara penyimpanannya di memori. Konsep ini memfokuskan perhatian kita pada apa yang bisa dilakukan oleh suatu tipe data dan operasi apa saja yang tersedia, tanpa perlu pusing memikirkan bagaimana logika internal atau alokasi memori itu dijalankan.



## Unguided 

### 1. Program data nilai Mahasiswa

#include <iostream>
#include <string>
using namespace std;

struct Mahasiswa {
    string nama;
    string nim;
    float uts;
    float uas;
    float tugas;
    float nilaiAkhir;
};

float hitungNilaiAkhir(float uts, float uas, float tugas) {
    return (0.3 * uts) + (0.4 * uas) + (0.3 * tugas);
}

int main() {
    Mahasiswa mhs[10];
    int jumlah;

    cout << "Jumlah mahasiswa (max 10) : ";
    cin >> jumlah;

    if (jumlah > 10) {
        cout << "Maksimal data hanya 10" << endl;
        return 0;
    }

    for (int i = 0; i < jumlah; i++) {
        cout << "\nData Mahasiswa ke-" << i + 1 << endl;
        cout << "Nama        : ";
        cin.ignore();
        getline(cin, mhs[i].nama);
        cout << "NIM         : ";
        cin >> mhs[i].nim;
        cout << "Nilai UTS   : ";
        cin >> mhs[i].uts;
        cout << "Nilai UAS   : ";
        cin >> mhs[i].uas;
        cout << "Nilai Tugas : ";
        cin >> mhs[i].tugas;

        mhs[i].nilaiAkhir = hitungNilaiAkhir(mhs[i].uts, mhs[i].uas, mhs[i].tugas);
    }

    for (int i = 0; i < jumlah; i++) {
        cout << "\nMahasiswa ke-" << i + 1 << endl;
        cout << "Nama        : " << mhs[i].nama << endl;
        cout << "NIM         : " << mhs[i].nim << endl;
        cout << "Nilai UTS   : " << mhs[i].uts << endl;
        cout << "Nilai UAS   : " << mhs[i].uas << endl;
        cout << "Nilai Tugas : " << mhs[i].tugas << endl;
        cout << "Nilai Akhir : " << mhs[i].nilaiAkhir << endl;
    }

    return 0;
}

##### Output 1
![Screenshot Output Unguided 1_1] https://github.com/daffaeca-a11y/Strukdat-modul-3/blob/main/output%201%20modul%203.jpeg

Program di atas digunakan untuk menghitung nilai mahasiswa dengan perbandingan 30% nilai UTS, 40% nilai UAS dan 30% nilai tugas


### 2. Program data pelajaran

main.cpp
#include <iostream>
#include "pelajaran.h"
using namespace std;

int main() {
    string namapel = "Struktur Data";
    string kodepel = "STD";
    pelajaran pel = create_pelajaran(namapel, kodepel);
    tampil_pelajaran(pel);
    return 0;
}

pelajaran.cpp
#include "pelajaran.h"
#include <iostream>
using namespace std;

pelajaran create_pelajaran(string namapel, string kodepel) {
    pelajaran pel;
    pel.namamapel = namapel;
    pel.kodemapel = kodepel;
    return pel;
}

void tampil_pelajaran(pelajaran pel) {
    cout << "nama layar : " << pel.namamapel << endl;
    cout << "kode : " << pel.kodemapel << endl;
}

pelajaran.h
#ifndef PELAJARAN_H
#define PELAJARAN_H

#include <string>
using namespace std;

struct pelajaran {
    string namamapel;
    string kodemapel;
};

pelajaran create_pelajaran(string namapel, string kodepel);
void tampil_pelajaran(pelajaran pel);

#endif

##### Output 2
![Screenshot Output Unguided 2_1] https://github.com/daffaeca-a11y/Strukdat-modul-3/blob/main/output%202%20modul%203.jpeg

Program menampilkan nama matkul dan kode matkul

### 3. Program Array 2D

#include <iostream>
using namespace std;

void cetakArray(int arr[3][3]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) cout << arr[i][j] << " ";
        cout << endl;
    }
}

void tukarPosisi(int A[3][3], int B[3][3], int r, int c) {
    int temp = A[r][c];
    A[r][c] = B[r][c];
    B[r][c] = temp;
}

void tukarPointer(int *p1, int *p2) {
    int temp = *p1;
    *p1 = *p2;
    *p2 = temp;
}

int main() {
    int A[3][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    int B[3][3] = {{9, 8, 7}, {6, 5, 4}, {3, 2, 1}};
    
    int *p1, *p2;

    cout << "Array A Awal:\n";
    cetakArray(A);
    cout << "\nArray B Awal:\n";
    cetakArray(B);

    tukarPosisi(A, B, 0, 1);

    p1 = &A[2][2];
    p2 = &B[2][2];
    tukarPointer(p1, p2);

    cout << "\n=====================\n";
    cout << "Hasil Setelah Ditukar:\n";
    cout << "Array A:\n";
    cetakArray(A);
    cout << "\nArray B:\n";
    cetakArray(B);

    return 0;
}

##### Output 3
![Screenshot Output Unguided 3_1] https://github.com/daffaeca-a11y/Strukdat-modul-3/blob/main/output%203%20modul%203.jpeg

penukaran nilai pada dua array 2D berukuran 3x3 dapat dilakukan melalui dua metode, yaitu pengaksesan indeks secara langsung dan penggunaan pointer.

## Kesimpulan
pada modul kali ini saya belajar mengenai konsep Abstract Data Type dengan memisahkan program menjadi 3 yaitu cpp, .h dan main.cpp

## Referensi


