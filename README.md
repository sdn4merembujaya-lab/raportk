# Rapor TK/PAUD 2026

Aplikasi rapor, sertifikat, dan piagam lomba anak untuk TK/PAUD dengan format **Kurikulum Merdeka**. Berjalan sepenuhnya di browser (satu file HTML), tanpa perlu server, database, atau instalasi.

## Fitur

- Login sekolah berbasis kode/NPSN dan PIN, hanya untuk sekolah yang terdaftar
- Pengelolaan data sekolah dan data siswa
- Cetak rapor per siswa atau massal (A4 / F4 / Letter)
- Cetak sertifikat piagam lomba dengan pilihan model dan foto anak
- Backup dan restore data dalam format JSON

## Cara Menjalankan

### Opsi 1: Langsung buka di browser
Cukup buka file `index.html` dengan browser (Chrome, Edge, atau Firefox).

### Opsi 2: Online lewat GitHub Pages
1. Buka repository ini di GitHub, lalu masuk ke **Settings → Pages**.
2. Pada bagian **Source**, pilih **Deploy from a branch**.
3. Pilih branch `main` dan folder `/ (root)`, lalu klik **Save**.
4. Setelah beberapa menit, aplikasi bisa diakses di `https://<username>.github.io/<nama-repo>/`.

## Mengatur Sekolah yang Boleh Login

Daftar sekolah ada di bagian `SEKOLAH_TERDAFTAR` di dalam `index.html`. Hanya sekolah yang tercantum di sana yang bisa masuk. Untuk menambah sekolah, buka `index.html`, cari `SEKOLAH_TERDAFTAR`, lalu tambahkan blok berikut setelah entri terakhir (jangan lupa tanda koma):

```js
"50204512": {
  kode: "50204512",
  nama: "TK Contoh Lain",
  operator: "Nama Kepala Sekolah",
  pin: "654321"
}
```

Kode harus huruf besar. Setelah itu, simpan, lalu commit dan push ulang ke GitHub.

## Catatan Penting

- **Data disimpan di browser** (localStorage) masing-masing perangkat. Data tidak otomatis sinkron antar perangkat, jadi gunakan fitur **Backup JSON** secara rutin.
- **PIN tersimpan di dalam kode** (`SEKOLAH_TERDAFTAR`). Karena kode bisa dilihat siapa pun di GitHub, PIN ini hanya pembatas sederhana. Ganti PIN contoh `123456` sebelum dipakai untuk data asli.
- Aplikasi ini tidak memiliki keamanan server. Jangan gunakan untuk data sensitif tanpa perlindungan tambahan.

## Struktur

```
.
├── index.html    # Seluruh aplikasi (HTML, CSS, dan JavaScript)
├── favicon.png   # Ikon tab browser
├── apple-touch-icon.png  # Ikon layar utama HP
├── logo.png      # Logo asli
├── og-image.png  # Gambar pratinjau saat tautan dibagikan
├── README.md
└── .gitignore
```

## Lisensi

Silakan tambahkan lisensi sesuai kebutuhan Anda.
