# praktikum6
# NAMA : MUHAMMAD GALIH FERI ABDILAH 
# KELAS : TI.24.A4
# NIM : 312410299
# MATKUL : BAHASA PEMOGRAMAN 

# PROGRAM PENGELOLAAN DATA MAHASISWA 
![image](https://github.com/user-attachments/assets/2779b123-deb3-4615-aeff-5806e7c5c9f9)
# PENJELASAN PROGRAM 
# Nilai akhir pelajar dihitung berdasarkan bobot sebagai berikut:
-Tugas: 30%
-UTS: 35%
-UAS: 35%.
# KOMPONEN PROGRAM 
# 1.STRUKTUR DATA 
Data siswa disimpan dalam daftar bernama data_list, yang berisi elemen kamus. Setiap kamus mewakili satu pelajar dengan format berikut:
```PYTHON
{
    'Nama': 'Nama Mahasiswa',
    'NIM': 'NIM Mahasiswa',
    'Tugas': 80.0,  # Nilai Tugas
    'UTS': 75.0,    # Nilai UTS
    'UAS': 85.0,    # Nilai UAS
    'Nilai Akhir': 81.5  # Hasil perhitungan nilai akhir
}
```
# 2.FUNGSI-FUNGSI UTAMA 
# oi_final_grade(tugas, uts, uas)
Fungsi ini menghitung nilai akhir siswa berdasarkan bobot masing-masing:

Tugas: 30%
UTS: 35%
UAS: 35%.
```PYTHON
def oi_final_grade(tugas, uts, uas):
    return (tugas * 0.30) + (uts * 0.35) + (uas * 0.35)
```
# lihat_data()
Fungsi ini menampilkan seluruh data siswa dalam format tabel. Jika data kosong, ditampilkan pesan "Tidak ada data!".
 ```PYTHON
def lihat_data():
    if not data_list:
        print("\nTidak ada data!")
    else:
        print("\nDaftar Nilai")
        print("=" * 70)
        print("| NO | NIM      | NAMA       | TUGAS   | UTS     | UAS     | AKHIR   |")
        print("=" * 70)
        for idx, student in enumerate(data_list, start=1):
            print(f"| {idx:<2} | {student['NIM']:<8} | {student['Nama']:<10} | "
                  f"{student['Tugas']:<8.2f} | {student['UTS']:<8.2f} | {student['UAS']:<8.2f} | "
                  f"{student['Nilai Akhir']:<8.2f} |")
        print("=" * 70)
```



