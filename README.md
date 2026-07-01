# Crackme 01 — Contoh Format Writeup

**Sumber:** https://crackmes.one/
**Level:** Easy
**Tools:** Ghidra, x64dbg, Detect It Easy (DIE)
**Status:** WIP

---

## 🎯 Tujuan Crackme

Berdasarkan deskripsi challenge, tujuan crackme ini adalah menganalisis executable untuk memahami bagaimana program melakukan validasi terhadap input pengguna. Target akhirnya adalah menemukan input yang dianggap benar atau memahami mekanisme validasi yang digunakan.

---

## 🔎 Triage Awal

### Informasi Dasar

Pada tahap awal saya membuka binary menggunakan Detect It Easy (DIE) untuk memperoleh informasi umum mengenai file.

Informasi yang perlu dicatat:

- Tipe file:
- Arsitektur:
- Compiler:
- Packer: Ya / Tidak

### Strings

Beberapa string yang menarik perhatian selama analisis awal antara lain:

- "Correct"
- "Wrong"
- "Enter Password"

String tersebut mengindikasikan bahwa program kemungkinan melakukan validasi terhadap input pengguna.

### Hipotesis Awal

Berdasarkan hasil triage, saya menduga terdapat fungsi yang membandingkan input pengguna dengan nilai tertentu. Langkah berikutnya adalah mencari referensi string tersebut di Ghidra untuk mengetahui alur program.

---

## 🧠 Proses Analisis

### 1. Membuka Binary Menggunakan Ghidra

Langkah pertama yang saya lakukan adalah mengimpor executable ke dalam Ghidra. Setelah proses analisis otomatis selesai, saya mencari fungsi `main()` dan melihat daftar string yang tersedia.

Saya kemudian menggunakan fitur **References** untuk mengetahui fungsi mana yang menggunakan string "Correct" dan "Wrong".

---

### 2. Mengikuti Alur Program

Setelah menemukan fungsi yang memanggil string tersebut, saya mengikuti alur program menuju bagian validasi input.

Pada tahap ini saya mencoba memahami apakah program menggunakan fungsi seperti:

- strcmp()
- memcmp()
- strlen()

atau mekanisme pembandingan lainnya.

---

### 3. Menggunakan x64dbg

Ketika masih belum memahami alur program, saya mencoba menjalankan executable menggunakan x64dbg.

Saya memasang breakpoint sebelum proses pembandingan input sehingga dapat mengamati perubahan register dan jalur eksekusi program.

Pendekatan ini membantu saya memahami bagaimana hasil pembandingan menentukan apakah program menampilkan pesan berhasil atau gagal.

---

### 4. Insight

Dari proses analisis saya memperoleh pemahaman mengenai lokasi fungsi validasi serta hubungan antara input pengguna dan proses pembandingan yang dilakukan program.

Insight utama diperoleh setelah mengikuti alur fungsi yang dipanggil dari `main()` menuju proses validasi.

---

## 📸 Screenshot Dianotasi

![Analisis Ghidra](screenshots/01-anotasi.png)

**Keterangan**

Pada screenshot ini diberi anotasi pada bagian fungsi yang melakukan proses validasi input. Panah menunjukkan lokasi instruksi atau fungsi penting yang menjadi titik awal analisis lebih lanjut. Anotasi dibuat agar lebih mudah memahami hubungan antara alur program dan proses pemeriksaan input.

---

## ✅ Solusi Akhir

Tuliskan hasil analisis setelah challenge benar-benar diselesaikan.

Contoh isi:

- lokasi validasi ditemukan
- mekanisme pembandingan berhasil dipahami
- alasan teknis mengapa solusi tersebut berhasil

Hindari hanya menuliskan password atau serial tanpa menjelaskan proses menemukannya.

---

## 💡 Refleksi

Melalui challenge ini saya belajar bahwa proses Reverse Engineering bukan hanya mencari jawaban akhir, tetapi memahami cara berpikir ketika menganalisis suatu program.

Saya juga mulai terbiasa menggunakan Ghidra untuk membaca hasil decompile dan memanfaatkan x64dbg ketika analisis statis saja belum cukup menjelaskan perilaku program. Ke depan saya ingin lebih banyak berlatih membaca kode assembly agar proses analisis menjadi lebih cepat dan akurat.
