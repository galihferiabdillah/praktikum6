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

# ubah_data()
Fungsi ini memungkinkan pengguna untuk memperbarui data siswa berdasarkan nomor urut. Setelah memilih nomor data, pengguna dapat memasukkan data baru. Nilai akhir diperbarui secara otomatis.
```PYTHON
def ubah_data():
    lihat_data()
    index = int(input("\nPilih nomor data yang ingin diubah: ")) - 1
    if 0 <= index < len(data_list):
        print("\nMasukkan data baru:")
        data_list[index]['NIM'] = input("NIM: ")
        data_list[index]['Nama'] = input("Nama: ")
        data_list[index]['Tugas'] = float(input("Nilai Tugas: "))
        data_list[index]['UTS'] = float(input("Nilai UTS: "))
        data_list[index]['UAS'] = float(input("Nilai UAS: "))
        data_list[index]['Nilai Akhir'] = oi_final_grade(
            data_list[index]['Tugas'],
            data_list[index]['UTS'],
            data_list[index]['UAS']
        )
        print("\nData berhasil diubah!")
    else:
        print("\nNomor data tidak ditemukan!")
```
# hapus_data()
Fungsi ini memungkinkan pengguna untuk menghapus data siswa berdasarkan nomor urut. Data akan dihapus dari daftar data_list.
```PYTHON
def hapus_data():
    lihat_data()
    index = int(input("\nPilih nomor data yang ingin dihapus: ")) - 1
    if 0 <= index < len(data_list):
        data_list.pop(index)
        print("\nData berhasil dihapus!")
    else:
        print("\nNomor data tidak ditemukan!")
```
# cari_data()
Fungsi ini mencari data siswa berdasarkan Nama atau NIM. Jika ditemukan, data yang sesuai akan ditampilkan dalam tabel. Jika tidak ditemukan, ditampilkan pesan "Data tidak ditemukan!".
```PYTHON
def cari_data():
    keyword = input("Masukkan NIM atau Nama yang ingin dicari: ").lower()
    found = [data for data in data_list if keyword in data['NIM'].lower() or keyword in data['Nama'].lower()]
    if found:
        print("\nHasil Pencarian:")
        print("=" * 70)
        print("| NO | NIM      | NAMA       | TUGAS   | UTS     | UAS     | AKHIR   |")
        print("=" * 70)
        for idx, student in enumerate(found, start=1):
            print(f"| {idx:<2} | {student['NIM']:<8} | {student['Nama']:<10} | "
                  f"{student['Tugas']:<8.2f} | {student['UTS']:<8.2f} | {student['UAS']:<8.2f} | "
                  f"{student['Nilai Akhir']:<8.2f} |")
        print("=" * 70)
    else:
        print("\nData tidak ditemukan!")
```
# 3.Program Utama (Menu Loop)
Menu program utama memungkinkan pengguna untuk memilih fitur melalui input:

*L: Melihat data. *T: Menambahkan data. *U: Mengubah data. *H: Menghapus data. *C: Mencari data. *K: Keluar dari program.

Program terus berjalan hingga pengguna memilih opsi K.
``` PYTHON
while True:
    print("\n[L]ihat, [T]ambah, [U]bah, [H]apus, [C]ari, [K]eluar")
    pilihan = input("Pilih menu: ").lower()

    if pilihan == 'l':
        lihat_data()
    elif pilihan == 't':
        tambah_data()
    elif pilihan == 'u':
        ubah_data()
    elif pilihan == 'h':
        hapus_data()
    elif pilihan == 'c':
        cari_data()
    elif pilihan == 'k':
        print("\nProgram selesai. Sampai jumpa!")
        break
    else:
        print("\nPilihan tidak valid!")
```
# screenshout VSC

![image](https://github.com/user-attachments/assets/542d9973-fc2c-4190-9ce6-6d80cf174014)

# Contoh output
Berikut adalah contoh tampilan tabel data:
# DAFTAR NILAI
# Daftar Nilai
# | NO | NIM | NAMA | TUGAS | UTS | UAS | AKHIR |
# berikut ini adalah hasil data yang telah di tapilkan di tabel di atas 
![4344](https://github.com/user-attachments/assets/3d12dd78-ea0f-455b-b8b0-0342c153b89c)

# dan ini adalah flowchartnya sebagai berikut :
![image](https://github.com/user-attachments/assets/823cf677-e682-4b8b-8d0f-3efdf05c20c4)








