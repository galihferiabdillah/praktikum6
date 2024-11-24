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

*Tugas: 30%
*UTS: 35%
*UAS: 35%.
