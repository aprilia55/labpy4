# praktikum 4 - Program Perhitungan Nilai Akhir Mahasiswa

Nama : Alfarizki Aprilia Putri 

Kelas : TI.24.A5 

Nim : 312410455

Mata Kuliah : Bahasa pemrograman 

## inisialisasi list  
```python

data_mahasiswa = [nama mahasiswa]
```
List `data mahasiswa` di gunakan untuk menyimpan data setiap mahasiswa.

setiap data di simpan dalam bentuk dictionary  dengan informasi : nama, nilai tugas, UTS, UAS, Nilai akhir 

## Input Data Mahasiswa :
```python

while True:
    print("\nMasukkan data mahasiswa:")
    nama = input("Nama: ")
    ...
```
Program meminta pengguna memasukkan nama mahasiswa dan nilai (tugas, UTS, UAS).

Nilai diinputkan dalam format angka, dan program memvalidasi apakah nilai tersebut berada dalam rentang 0-100.

## Validasi nilai :

```python

try:
    nilai_tugas = float(input("Nilai Tugas (0-100): "))
    nilai_uts = float(input("Nilai UTS (0-100): "))
    nilai_uas = float(input("Nilai UAS (0-100): "))
except ValueError:
    print("Input harus berupa angka. Silakan coba lagi.")
    continue

if not (0 <= nilai_tugas <= 100 and 0 <= nilai_uts <= 100 and 0 <= nilai_uas <= 100):
    print("Nilai harus berada dalam rentang 0-100. Silakan coba lagi.")
    continue

```
`Try Except` : Digunakan untuk memastikan input berupa angka, sehingga program tidak error jika pengguna memasukkan data yang salah.

**Validasi rentang** : Program memastikan nilai berada di antara 0 dan 100.

## Perhitungan niali akhir 

```python

nilai_akhir = (nilai_tugas * 0.3) + (nilai_uts * 0.35) + (nilai_uas * 0.35)

```
Nilai akhir dihitung berdasarkan bobot :

Tugas: **30%**

UTS: **35%**

UAS: **35%**


## Menyimpan Data Ke dalam list 

```python

data_mahasiswa.append({
    "nama": nama,
    "nilai_tugas": nilai_tugas,
    "nilai_uts": nilai_uts,
    "nilai_uas": nilai_uas,
    "nilai_akhir": nilai_akhir
})

```
Setiap data mahasiswa yang baru diinput ditambahkan ke list `data_mahasiswa` dalam bentuk dictionary.

## Menghentikan atau melanjutkan Input 

```python

lanjut = input("Apakah ingin menambahkan data lagi? (y/t): ").lower()
if lanjut == 't':
    break
```
Program memberikan opsi kepada pengguna untuk melanjutkan `(y)` atau berhenti `(t)` menginput data.

## Menampilkan data dalam format tabel

```python

print("\nDaftar Data Mahasiswa:")
print("=" * 50)
print(f"{'No.':<4} {'Nama':<15} {'Tugas':<7} {'UTS':<7} {'UAS':<7} {'Akhir':<7}")
print("=" * 50)

for i, mahasiswa in enumerate(data_mahasiswa, start=1):
    print(f"{i:<4} {mahasiswa['nama']:<15} {mahasiswa['nilai_tugas']:<7.2f} "
          f"{mahasiswa['nilai_uts']:<7.2f} {mahasiswa['nilai_uas']:<7.2f} {mahasiswa['nilai_akhir']:<7.2f}")

print("=" * 50)

```
Header tabel : Program mencetak nama kolom seperti nomor, nama, tugas, UTS, UAS, dan nilai akhir.

Pengisian data : Menggunakan `enumerate` untuk memberikan nomor urut dan mengakses setiap `data mahasiswa` di list data_mahasiswa.

Format angka : Nilai tugas, UTS, UAS, dan nilai akhir ditampilkan dengan dua angka di belakang koma.

## Contoh Output Program 

```python

Masukkan data mahasiswa:
Nama: april
Nilai Tugas (0-100): 85
Nilai UTS (0-100): 88
Nilai UAS (0-100): 90
Apakah ingin menambahkan data lagi? (y/t): y

Masukkan data mahasiswa:
Nama: safa
Nilai Tugas (0-100): 75
Nilai UTS (0-100): 80
Nilai UAS (0-100): 85
Apakah ingin menambahkan data lagi? (y/t): t

```
## Flow Chart 
![foto](https://github.com/aprilia55/labpy4/blob/8b2fed1209896a40976a259fd07261405b33f2d6/WhatsApp%20Image%202024-11-18%20at%2021.16.50.jpeg)

## Hasil Output 
![foto](https://github.com/aprilia55/labpy4/blob/f624e6c02442f1244821865ee00eab3b3c229b32/Screen%20Shot%202024-11-18%20at%2011.32.26.png)
