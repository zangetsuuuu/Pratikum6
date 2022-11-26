Nama: Rafif Isdarufa Athallah

NIM: 312210299

Kelas: TI.22.A3

---

## Latihan

- Buat *dictionary* daftar kontak

```python
kontak = {"Ari": "081267888", "Dina": "087677776"}
```

- Menampilkan *value* dalam *dictionary*

```python
print(kontak["Ari"])

# Output = 081267888
```

- Menambahkan kontak baru kedalam *dictionary*

```python
kontak["Riko"] = "087654544"
```

- Mengubah *value* pada *dictionary*

```python
kontak["Dina"] = "088999776"
```

- Menampilkan semua nama/*keys* dalam *dictionary*

```python
print(kontak.keys())

# Output = dict_keys(['Ari', 'Dina', 'Riko'])
```

- Menampilkan semua nomor/*values* dalam *dictionary*

```python
print(kontak.values())

# Output = dict_values(['081267888', '087677776', '087654544'])
```

- Menampilkan daftar nama dan nomor dalam *dictionary*

```python
print(kontak.items())

# Output = dict_items([('Ari', '081267888'), ('Dina', '087677776'), ('Riko', '087654544')])
```

- Menghapus kontak pada *dictionary*

```python
del kontak["Dina"]
```

---

## Tugas Pratikum

### Flowchart

![Flowchart.jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Flowchart.jpg)

---

- Buat sebuah *dictionary* kosong untuk menampung data

```python
data_mahasiswa = {}
```

- Lakukan perulangan dengan menggunakan `while`
- Buat variabel untuk menginput data

```python
while True:
    menu = input("[(L)ihat,  (T)ambah,  (U)bah,  (H)apus,  (C)ari,  (K)eluar]: ")
    print()
```

- Jika *user* menginput 'l / L', maka akan menampilkan daftar nilai
- Apabila belum ada data dalam *dictionary*, maka akan menampilkan daftar nilai kosong

```python
    if (menu.lower() == "l"):
        print("[ Daftar Nilai ]")
        if data_mahasiswa.items():
            print("=====================================================================================================")
            print("| No |           Nama           |       NIM       |   Tugas   |   UTS   |   UAS   |   Nilai Akhir   |")
            print("=====================================================================================================")
            i = 0
            for j in data_mahasiswa.items():
                i += 1
                print("| {no:2d} | {0:24s} | {1:15d} | {2:9d} | {3:7d} | {4:7d} | {5:15f} |".format(j[0], j[1][0], j[1][1], j[1][2], j[1][3], j[1][4], no=i))
            print("=====================================================================================================\n")

        else:
            print("=====================================================================================================")
            print("| No |           Nama           |       NIM       |   Tugas   |   UTS   |   UAS   |   Nilai Akhir   |")
            print("=====================================================================================================")
            print("|                                          TIDAK ADA DATA                                           |")
            print("=====================================================================================================\n")
```

- Jika *user* menginput 't/T', maka *user* akan diminta untuk menginput data
- Apabila sudah menginput semua data, maka data-data tersebut akan dimasukkan kedalam *dictionary*

```python
    elif (menu.lower() == "t"):
        print("[ Tambah Data ]")
        nama = input("Nama        : ")
        nim = int(input("NIM         : "))
        tugas = int(input("Nilai Tugas : "))
        uts = int(input("Nilai UTS   : "))
        uas = int(input("Nilai UAS   : "))
        print("Data berhasil ditambahkan!\n")
        total = (tugas * 30 / 100) + (uts * 35 / 100) + (uas * 35 / 100)
        data_mahasiswa[nama] = nim, tugas, uts, uas, total
```

- Jika *user* menginput 'u / U', maka *user* dapat mengubah data dengan memasukkan data nama yang ingin diubah kemudian menginput data baru untuk menggantikan data sebelumnya
- Apabila data nama tidak ada dalam *dictionary*, maka program akan menampilkan "Data tidak ditemukan!"

```python
    elif (menu.lower() == "u"):
        print("[ Ubah Data ]")
        nama = input("Masukkan nama : ")
        if nama in data_mahasiswa.keys():
            nim = int(input("NIM           : "))
            tugas = int(input("Nilai Tugas   : "))
            uts = int(input("Nilai UTS     : "))
            uas = int(input("Nilai UAS     : "))
            total = (tugas * 30 / 100) + (uts * 35 / 100) + (uas * 35 / 100)
            data_mahasiswa[nama] = nim, tugas, uts, uas, total
            print("Data berhasil diubah!\n")

        else:
            print("Data tidak ditemukan!\n")
```

- Jika *user* menginput 'h / H', maka *user* dapat menghapus data dengan memasukkan data nama yang ingin dihapus kemudian data tersebut akan dihapus dari *dictionary*
- Apabila data nama tidak ada dalam *dictionary*, maka program akan menampilkan "Data tidak ditemukan!"

```python
    elif (menu.lower() == "h"):
        print("[ Hapus Data ]")
        nama = input("Masukkan nama : ")
        if nama in data_mahasiswa.keys():
            del data_mahasiswa[nama]
            print("Data berhasil dihapus!\n")

        else:
            print("Data tidak ditemukan!\n")
```

- Jika *user* menginput 'c / C', maka *user* dapat mencari data dengan memasukkan data nama yang ingin dicari kemudian data akan ditampilkan
- Apabila data nama tidak ada dalam *dictionary*, maka program akan menampilkan "Data tidak ditemukan!"

```python
    elif (menu.lower() == "c"):
        print("[ Cari Data ]")
        nama = input("Masukkan nama : ")
        if nama in data_mahasiswa.keys():
            print("================================================================================================")
            print("|           Nama           |       NIM       |   Tugas   |   UTS   |   UAS   |   Nilai Akhir   |")
            print("================================================================================================")
            print("| {0:24s} | {1:15d} | {2:9d} | {3:7d} | {4:7d} | {5:15f} |"
                  .format(nama, data_mahasiswa[nama][0], data_mahasiswa[nama][1], data_mahasiswa[nama][2], data_mahasiswa[nama][3], data_mahasiswa[nama][4]))
            print("================================================================================================\n")

        else:
            print("================================================================================================")
            print("|           Nama           |       NIM       |   Tugas   |   UTS   |   UAS   |   Nilai Akhir   |")
            print("================================================================================================")
            print("|                                     DATA TIDAK DITEMUKAN                                     |")
            print("================================================================================================\n")
```

- Jika *user* menginput 'k / K', maka program akan berhenti

```python
    elif menu.lower() == "k":
        print("> Anda telah keluar dari program")
        break
```

- Jika *user* menginput kode yang tidak sesuai, maka *user* akan diminta menginput kembali

```python
    else:
        print("Kode tidak valid!\n")
```

---

#### Menu lihat

![Lihat.jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Lihat.jpg)

#### Menu tambah

![Tambah(1).jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Tambah(1).jpg)
![Tambah(2).jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Tambah(2).jpg)

#### Menu ubah

![Ubah(1).jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Ubah(1).jpg)
![Ubah(2).jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Ubah(2).jpg)

#### Menu hapus

![Hapus(1).jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Hapus(1).jpg)
![Hapus(2).jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Hapus(2).jpg)

#### Menu cari

![Cari.jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Cari.jpg)

#### Menu keluar

![Keluar.jpg](https://github.com/zangetsuuuu/Pratikum6/blob/e7a1f99d32a1168920b0fda98ae3b8e5045cc7a0/gambar/Keluar.jpg)

### Sekian, terimakasih
