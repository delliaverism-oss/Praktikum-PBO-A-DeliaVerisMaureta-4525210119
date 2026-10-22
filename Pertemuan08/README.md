# LAPORAN UTS PRAKTIKUM PEMROGRAMAN BERBASIS OBJEK

| Informasi Proyek | Keterangan |
| :--- | :--- |
| **Mata Kuliah** | Pemrograman Berorientasi Objek (PBO) |
| **Kelas** | A |
| **PJ** | [Muhammad Shehan Algi] |
| **Tema** | [Administrasi Arsip Rumah Sakit] |
| **Tanggal** | [Kamis, 22 - 10 - 2026] |
| **Nama** | [Delia Veris Maureta] |
| **NPM** | [4525210119] |

---

## Detail Pengerjaan & Anggota Kelompok

| Nama | NPM | Tugas / Fitur yang Dikerjakan |
| :--- | :--- | :--- |
| [El-jordan Fathi Arrizky] | [4525210115] | [Penyakit.Java] |
| [Muhammad Farrel Rizky] | [4525210117] | [RumahSakit.Java] |
| [Azzahra Navisha] | [4525210118] | [Dokter.Java] |
| [Delia Veris Maureta] | [4525210119] | [Pasien.Java] |
| [Muhammad Rafif Akbar] | [4525210125] | [Alamat.Java] |
| [Arsanti Nur Indriani] | [4525210126] | [Main.Java] |
| [Nisrina Akilla] | [4525210128] | [GA MASUK] |
---

## Deskripsi Proyek
> [Jelaskan secara singkat aplikasi apa yang dibangun pada proyek UTS ini, apa tujuan utamanya, dan masalah apa yang ingin diselesaikan.]

**Daftar Fitur:**
1. Nama Penyakit Pasien
2. Nama Rumah Sakit
3. Nama Dokter
4. Nama Pasien
5. Alamat Pasien

---

## 1. Implementasi Java

### 1.1. File: `Penyakit.java`
**Penjelasan Kode:**
> [Penyakit.java ini mendefinisikan class Penyakit yang menyimpan data penyakit pasien, yaitu nama dan tingkat keparahan. Atribut dibuat private dan diakses lewat getter dan setter (enkapsulasi). Data diisi lewat konstruktor Penyakit(String nama, Tingkat tingkat). Di dalam class ini ada enum bersarang bernama Tingkat dengan tiga nilai tetap, yaitu RINGAN, SEDANG, dan BERAT. Setiap nilai punya label yang diisi lewat konstruktor enum dan dibaca dengan getLabel(). Dengan enum, tingkat penyakit tidak bisa diisi sembarang teks. Method toString() di override agar objek Penyakit tercetak rapi, misalnya Influenza (Tingkat: Ringan).]

**Screenshot Kode:**
<img width="954" height="936" alt="image" src="https://github.com/user-attachments/assets/b67f2b54-d938-4227-a612-f380d470efaa" />

### 1.2. File: `RumahSakit.java`
**Penjelasan Kode:**
> [RumahSakit.java ini berisi class RumahSakit, yaitu pusat pengelolaan arsip. Class ini punya konstanta MAKS_DOKTER = 10 (static final) sebagai batas jumlah dokter, dan variabel static totalSurat yang menghitung seluruh surat yang diarsipkan. Atribut alamat bertipe Alamat, serta dua ArrayList (daftarDokter dan daftarPasien) menunjukkan relasi objek, karena rumah sakit memiliki banyak dokter dan banyak pasien (has-a, agregasi). Method tambahDokter() menambah dokter selama kapasitas belum penuh, dan daftarkanPasien() menambah pasien sambil menaikkan totalSurat. Method cetakSemuaArsip() menggabungkan dokter dan pasien ke dalam satu ArrayList, lalu memanggil cetakArsip() pada setiap elemen. Ini contoh polimorfisme, karena Dokter dan Pasien dicetak dengan cara masing-masing lewat satu tipe yang sama, yaitu interface Arsipable.]

**Screenshot Kode:**
<img width="1144" height="950" alt="image" src="https://github.com/user-attachments/assets/beca2c78-b657-46f5-85c9-2424936822b7" />
<img width="1001" height="540" alt="image" src="https://github.com/user-attachments/assets/030b4acc-4ecd-4b63-9b87-57f2ba67caf9" />

### 1.3. File: `Dokter.java`
**Penjelasan Kode:**
> [Pasien.java ini memuat tiga bagian.

Interface Arsipable, yang berisi konstanta KATEGORI = "SURAT-RS" dan method cetakArsip() yang wajib diimplementasikan semua class yang bisa diarsipkan.
Abstract class Orang, yang mengimplementasikan Arsipable dan menjadi superclass bagi Dokter dan Pasien. Class ini menyimpan atribut umum nama dan umur (private, dengan getter/setter), method abstrak getPeran() yang harus diisi oleh subclass, dan method getInfo() yang memakai getPeran().
Class Dokter, yang mewarisi Orang (extends) dan menambah atribut spesialis. Konstruktornya memanggil super(nama, umur) untuk mengisi data dari superclass. Dokter meng-override getPeran() (mengembalikan “Dokter”), getInfo() (memanggil super.getInfo() lalu menambahkan spesialis), dan cetakArsip() (memberi awalan [SURAT-RS]). Ketiganya contoh polimorfisme (overriding).]

**Screenshot Kode:**
<img width="933" height="954" alt="image" src="https://github.com/user-attachments/assets/af0e7f03-19e8-4a34-8597-f2f6d6c0db5c" />
<img width="971" height="512" alt="image" src="https://github.com/user-attachments/assets/453ccebd-7603-4534-b30c-3779d5d27f16" />

### 1.4. File: `Pasien.java`
**Penjelasan Kode:**
> [Pasien.java juga mewarisi Orang, sehingga memakai atribut nama dan umur dari superclass. Atribut khususnya adalah alamat (objek Alamat), penyakit (objek Penyakit), dan dokter (objek Dokter), yang membentuk relasi antar objek. Variabel static jumlahPasien menghitung semua pasien yang dibuat, dan atribut final nomorArsip dibuat otomatis di konstruktor dengan format SURAT-RS/001, SURAT-RS/002, dan seterusnya. Karena final, nomor ini tidak bisa diubah setelah dibuat. Ada dua konstruktor (overloading): satu menerima dokter, dan satu lagi tanpa dokter yang memanggil this(..., null). Method getPeran() dan cetakArsip() di-override dari superclass dan interface. Jika dokter masih null, arsip mencetak “Belum ditentukan”.]

**Screenshot Kode:**
<img width="1078" height="945" alt="image" src="https://github.com/user-attachments/assets/85097b62-fb04-4c1b-847e-9808c98dcca6" />
<img width="1007" height="372" alt="image" src="https://github.com/user-attachments/assets/830de487-cfec-4b53-a36c-cf0d86a14f3c" />

### 1.5. File: `Alamat.java`
**Penjelasan Kode:**
> [Alamat.java menyimpan data alamat berupa jalan, kota, dan provinsi. Atributnya private dan diakses lewat getter dan setter (enkapsulasi). Nilai atribut diisi melalui konstruktor dengan parameter jalan, kota, dan provinsi. Class ini juga punya konstanta NEGARA = "Indonesia" yang bertipe public static final, sehingga nilainya sama untuk semua objek dan tidak bisa diubah. Method toString() di-override untuk menggabungkan seluruh bagian alamat menjadi satu teks. Class ini dipakai oleh RumahSakit dan Pasien.]

**Screenshot Kode:**
<img width="918" height="834" alt="image" src="https://github.com/user-attachments/assets/9210a1a4-2c10-4dfb-bdeb-b6815797eb56" />

### 1.6. File: `Main.java`
**Penjelasan Kode:**
> [Main.java adalah program utama yang menjalankan seluruh alur. Pertama dibuat objek RumahSakit (“RS Sehat Sentosa”) beserta Alamat-nya. Lalu dibuat tiga objek Dokter (d1, d2, d3) yang ditambahkan lewat tambahDokter(). Setelah itu dibuat tiga objek Pasien, masing-masing dengan Alamat dan Penyakit (memakai enum Penyakit.Tingkat). p1 langsung diberi dokter d1 lewat konstruktor, p2 diberi dokter d2 lewat setDokter(), dan p3 tidak diberi dokter sehingga arsipnya menampilkan “Belum ditentukan”. Semua pasien didaftarkan dengan daftarkanPasien(), lalu cetakSemuaArsip() mencetak arsip dokter dan pasien. Terakhir, program menampilkan total pasien (Pasien.getJumlahPasien()) dan total surat (RumahSakit.getTotalSurat()) yang diambil dari variabel static.]

**Screenshot Kode:**
<img width="1074" height="816" alt="image" src="https://github.com/user-attachments/assets/d223b5dc-e6b0-4ebb-a570-0be61d9edcd8" />

### Output
**Hasil Running Program (Java):**
<img width="1042" height="608" alt="image" src="https://github.com/user-attachments/assets/ae82e1fa-c4f1-4a32-8bea-ed6fc31c604b" />

---

## 3. Kesimpulan
> Proyek kelompok kami untuk OOP nya memilih Java karena dikelompok kami hampir semuanya lebih paham dengan Java di banding PHP. Dan untuk materi yang kami pakai semua materi dari pertemuan 1-7 yaitu: 01 (Kelas, Objek, dan Enkapsulasi), 02 (Koncstruktor, Static, dan Konstanta), 03 (Pewarisan), 04 (Polimorfisme), 05 (Abstract, Interface, Enum), 06 (Relasi Objek). Proyek kami membuat Admnistrasi Arsip Rumah Sakit yang nantinya hasilnya ada keterangan seperti Nama Rumah Sakit, Penyakit Pasiennya, Dokter yang memeriksanya, nama Pasiennya, Alamat si pasiennya dan pastinya ada Main.Javanya untuk melihat outputnya.